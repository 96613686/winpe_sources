# IsClientSystem

- ea: `0x18000c9f8`
- end: `0x18000cb96`
- name: `IsClientSystem`
- size: `414`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cb9c`

## callees

- `0x18000c9f8`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000cadd`
- `ntdll!RtlAllocateHeap` at `0x18000cadd`
- `ntdll!RtlFreeHeap` at `0x18000cb22`
- `ntdll!RtlFreeHeap` at `0x18000cb63`
- `ntdll!RtlFreeHeap` at `0x18000cb22`
- `ntdll!RtlFreeHeap` at `0x18000cb63`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ca79`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ca79`
- `ntdll!NtQueryInformationToken` at `0x18000caaf`
- `ntdll!NtQueryInformationToken` at `0x18000cb06`
- `ntdll!NtQueryInformationToken` at `0x18000caaf`
- `ntdll!NtQueryInformationToken` at `0x18000cb06`
- `ntdll!RtlEqualSid` at `0x18000cb44`
- `ntdll!RtlEqualSid` at `0x18000cb44`

## pseudocode

```c
__int64 __fastcall IsClientSystem(HANDLE TokenHandle)
{
  int v2; // edi
  NTSTATUS v4; // eax
  PSID *Heap; // rbx
  unsigned int v6; // esi
  ULONG ReturnLength; // [rsp+60h] [rbp-49h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+64h] [rbp-45h] BYREF
  _BYTE TokenInformation[112]; // [rsp+70h] [rbp-39h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  ReturnLength = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = 1;
  if ( !Sid1 && RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid1) < 0 )
  {
    Sid1 = 0;
    return 0;
  }
  v4 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x64u, &ReturnLength);
  if ( v4 >= 0 )
  {
    v2 = 0;
    Heap = (PSID *)TokenInformation;
  }
  else
  {
    if ( v4 != -1073741789 )
      return 0;
    Heap = (PSID *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag + 0x40000, ReturnLength);
    if ( !Heap )
      return 0;
    if ( NtQueryInformationToken(TokenHandle, TokenUser, Heap, ReturnLength, &ReturnLength) < 0 )
    {
      RtlFreeHeap(BaseSrvHeap, 0, Heap);
      return 0;
    }
  }
  v6 = RtlEqualSid(Sid1, *Heap);
  if ( v2 )
    RtlFreeHeap(BaseSrvHeap, 0, Heap);
  return v6;
}

```

## disassembly

```asm
0x18000c9f8  mov     [rsp-8+arg_8], rbx
0x18000c9fd  mov     [rsp-8+arg_10], rsi
0x18000ca02  push    rbp
0x18000ca03  push    rdi
0x18000ca04  push    r14
0x18000ca06  lea     rbp, [rsp-47h]
0x18000ca0b  sub     rsp, 0F0h
0x18000ca12  mov     rax, cs:__security_cookie
0x18000ca19  xor     rax, rsp
0x18000ca1c  mov     [rbp+57h+var_20], rax
0x18000ca20  xor     r14d, r14d
0x18000ca23  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18000ca29  cmp     cs:Sid1, r14
0x18000ca30  mov     rsi, rcx
0x18000ca33  mov     [rbp+57h+ReturnLength], r14d
0x18000ca37  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x18000ca3b  lea     edi, [r14+1]
0x18000ca3f  jnz     short loc_18000CA97
0x18000ca41  lea     rax, Sid1
0x18000ca48  xor     r9d, r9d; SubAuthority1
0x18000ca4b  mov     [rsp+100h+Sid], rax; Sid
0x18000ca50  lea     r8d, [r14+12h]; SubAuthority0
0x18000ca54  mov     [rsp+100h+SubAuthority7], r14d; SubAuthority7
0x18000ca59  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000ca5d  mov     [rsp+100h+SubAuthority6], r14d; SubAuthority6
0x18000ca62  mov     dl, dil; SubAuthorityCount
0x18000ca65  mov     [rsp+100h+SubAuthority5], r14d; SubAuthority5
0x18000ca6a  mov     [rsp+100h+SubAuthority4], r14d; SubAuthority4
0x18000ca6f  mov     [rsp+100h+SubAuthority3], r14d; SubAuthority3
0x18000ca74  mov     [rsp+100h+SubAuthority2], r14d; SubAuthority2
0x18000ca79  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000ca80  nop     dword ptr [rax+rax+00h]
0x18000ca85  test    eax, eax
0x18000ca87  jns     short loc_18000CA97
0x18000ca89  mov     cs:Sid1, r14
0x18000ca90  xor     eax, eax
0x18000ca92  jmp     loc_18000CB71
0x18000ca97  lea     rax, [rbp+57h+ReturnLength]
0x18000ca9b  mov     r9d, 64h ; 'd'; TokenInformationLength
0x18000caa1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000caa5  mov     qword ptr [rsp+100h+SubAuthority2], rax; ReturnLength
0x18000caaa  mov     edx, edi; TokenInformationClass
0x18000caac  mov     rcx, rsi; TokenHandle
0x18000caaf  call    cs:__imp_NtQueryInformationToken
0x18000cab6  nop     dword ptr [rax+rax+00h]
0x18000cabb  test    eax, eax
0x18000cabd  jns     short loc_18000CB33
0x18000cabf  cmp     eax, 0C0000023h
0x18000cac4  jnz     short loc_18000CA90
0x18000cac6  mov     edx, cs:BaseSrvTag
0x18000cacc  mov     r8d, [rbp+57h+ReturnLength]; Size
0x18000cad0  add     edx, 40000h; Flags
0x18000cad6  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000cadd  call    cs:__imp_RtlAllocateHeap
0x18000cae4  nop     dword ptr [rax+rax+00h]
0x18000cae9  mov     rbx, rax
0x18000caec  test    rax, rax
0x18000caef  jz      short loc_18000CA90
0x18000caf1  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18000caf5  lea     rax, [rbp+57h+ReturnLength]
0x18000caf9  mov     r8, rbx; TokenInformation
0x18000cafc  mov     qword ptr [rsp+100h+SubAuthority2], rax; ReturnLength
0x18000cb01  mov     edx, edi; TokenInformationClass
0x18000cb03  mov     rcx, rsi; TokenHandle
0x18000cb06  call    cs:__imp_NtQueryInformationToken
0x18000cb0d  nop     dword ptr [rax+rax+00h]
0x18000cb12  test    eax, eax
0x18000cb14  jns     short loc_18000CB3A
0x18000cb16  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000cb1d  mov     r8, rbx; P
0x18000cb20  xor     edx, edx; Flags
0x18000cb22  call    cs:__imp_RtlFreeHeap
0x18000cb29  nop     dword ptr [rax+rax+00h]
0x18000cb2e  jmp     loc_18000CA90
0x18000cb33  mov     edi, r14d
0x18000cb36  lea     rbx, [rbp+57h+TokenInformation]
0x18000cb3a  mov     rdx, [rbx]; Sid2
0x18000cb3d  mov     rcx, cs:Sid1; Sid1
0x18000cb44  call    cs:__imp_RtlEqualSid
0x18000cb4b  nop     dword ptr [rax+rax+00h]
0x18000cb50  movzx   esi, al
0x18000cb53  test    edi, edi
0x18000cb55  jz      short loc_18000CB6F
0x18000cb57  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000cb5e  mov     r8, rbx; P
0x18000cb61  xor     edx, edx; Flags
0x18000cb63  call    cs:__imp_RtlFreeHeap
0x18000cb6a  nop     dword ptr [rax+rax+00h]
0x18000cb6f  mov     eax, esi
0x18000cb71  mov     rcx, [rbp+57h+var_20]
0x18000cb75  xor     rcx, rsp; StackCookie
0x18000cb78  call    __security_check_cookie
0x18000cb7d  lea     r11, [rsp+100h+var_10]
0x18000cb85  mov     rbx, [r11+28h]
0x18000cb89  mov     rsi, [r11+30h]
0x18000cb8d  mov     rsp, r11
0x18000cb90  pop     r14
0x18000cb92  pop     rdi
0x18000cb93  pop     rbp
0x18000cb94  retn
```
