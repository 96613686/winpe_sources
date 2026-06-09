# IsClientSystem

- ea: `0x18000c61c`
- end: `0x18000c7bc`
- name: `IsClientSystem`
- size: `416`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c7c4`

## callees

- `0x18000c61c`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c705`
- `ntdll!RtlAllocateHeap` at `0x18000c705`
- `ntdll!RtlFreeHeap` at `0x18000c74f`
- `ntdll!RtlFreeHeap` at `0x18000c789`
- `ntdll!RtlFreeHeap` at `0x18000c74f`
- `ntdll!RtlFreeHeap` at `0x18000c789`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c69f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c69f`
- `ntdll!NtQueryInformationToken` at `0x18000c6d7`
- `ntdll!NtQueryInformationToken` at `0x18000c733`
- `ntdll!NtQueryInformationToken` at `0x18000c6d7`
- `ntdll!NtQueryInformationToken` at `0x18000c733`
- `ntdll!RtlEqualSid` at `0x18000c76a`
- `ntdll!RtlEqualSid` at `0x18000c76a`

## pseudocode

```c
__int64 __fastcall IsClientSystem(HANDLE TokenHandle)
{
  PSID *Heap; // rbx
  int v3; // esi
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  ULONG ReturnLength; // [rsp+60h] [rbp-49h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+64h] [rbp-45h] BYREF
  _BYTE TokenInformation[112]; // [rsp+70h] [rbp-39h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Heap = (PSID *)TokenInformation;
  ReturnLength = 0;
  v3 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( !Sid1 && RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid1) < 0 )
  {
    Sid1 = 0;
    return 0;
  }
  v5 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x64u, &ReturnLength);
  if ( v5 < 0 )
  {
    if ( v5 != -1073741789 )
      return 0;
    Heap = (PSID *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag + 0x40000, ReturnLength);
    if ( !Heap )
      return 0;
    v3 = 1;
    if ( NtQueryInformationToken(TokenHandle, TokenUser, Heap, ReturnLength, &ReturnLength) < 0 )
    {
      RtlFreeHeap(BaseSrvHeap, 0, Heap);
      return 0;
    }
  }
  v6 = RtlEqualSid(Sid1, *Heap);
  if ( v3 )
    RtlFreeHeap(BaseSrvHeap, 0, Heap);
  return v6;
}

```

## disassembly

```asm
0x18000c61c  mov     [rsp-8+arg_8], rbx
0x18000c621  mov     [rsp-8+arg_10], rsi
0x18000c626  push    rbp
0x18000c627  push    rdi
0x18000c628  push    r14
0x18000c62a  lea     rbp, [rsp-47h]
0x18000c62f  sub     rsp, 0F0h
0x18000c636  mov     rax, cs:__security_cookie
0x18000c63d  xor     rax, rsp
0x18000c640  mov     [rbp+57h+var_20], rax
0x18000c644  xor     r14d, r14d
0x18000c647  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18000c64d  cmp     cs:Sid1, r14
0x18000c654  lea     rbx, [rbp+57h+TokenInformation]
0x18000c658  mov     rdi, rcx
0x18000c65b  mov     [rbp+57h+ReturnLength], r14d
0x18000c65f  mov     esi, r14d
0x18000c662  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x18000c666  jnz     short loc_18000C6BD
0x18000c668  lea     rax, Sid1
0x18000c66f  xor     r9d, r9d; SubAuthority1
0x18000c672  mov     [rsp+100h+Sid], rax; Sid
0x18000c677  lea     r8d, [r14+12h]; SubAuthority0
0x18000c67b  mov     [rsp+100h+SubAuthority7], r14d; SubAuthority7
0x18000c680  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000c684  mov     [rsp+100h+SubAuthority6], r14d; SubAuthority6
0x18000c689  mov     dl, 1; SubAuthorityCount
0x18000c68b  mov     [rsp+100h+SubAuthority5], r14d; SubAuthority5
0x18000c690  mov     [rsp+100h+SubAuthority4], r14d; SubAuthority4
0x18000c695  mov     [rsp+100h+SubAuthority3], r14d; SubAuthority3
0x18000c69a  mov     [rsp+100h+SubAuthority2], r14d; SubAuthority2
0x18000c69f  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c6a6  nop     dword ptr [rax+rax+00h]
0x18000c6ab  test    eax, eax
0x18000c6ad  jns     short loc_18000C6BD
0x18000c6af  mov     cs:Sid1, r14
0x18000c6b6  xor     eax, eax
0x18000c6b8  jmp     loc_18000C797
0x18000c6bd  mov     r9d, 64h ; 'd'; TokenInformationLength
0x18000c6c3  lea     rax, [rbp+57h+ReturnLength]
0x18000c6c7  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000c6cb  mov     qword ptr [rsp+100h+SubAuthority2], rax; ReturnLength
0x18000c6d0  mov     rcx, rdi; TokenHandle
0x18000c6d3  lea     edx, [r9-63h]; TokenInformationClass
0x18000c6d7  call    cs:__imp_NtQueryInformationToken
0x18000c6de  nop     dword ptr [rax+rax+00h]
0x18000c6e3  test    eax, eax
0x18000c6e5  jns     short loc_18000C760
0x18000c6e7  cmp     eax, 0C0000023h
0x18000c6ec  jnz     short loc_18000C6B6
0x18000c6ee  mov     edx, cs:BaseSrvTag
0x18000c6f4  mov     r8d, [rbp+57h+ReturnLength]; Size
0x18000c6f8  add     edx, 40000h; Flags
0x18000c6fe  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000c705  call    cs:__imp_RtlAllocateHeap
0x18000c70c  nop     dword ptr [rax+rax+00h]
0x18000c711  mov     rbx, rax
0x18000c714  test    rax, rax
0x18000c717  jz      short loc_18000C6B6
0x18000c719  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18000c71d  lea     rax, [rbp+57h+ReturnLength]
0x18000c721  mov     esi, 1
0x18000c726  mov     qword ptr [rsp+100h+SubAuthority2], rax; ReturnLength
0x18000c72b  mov     edx, esi; TokenInformationClass
0x18000c72d  mov     r8, rbx; TokenInformation
0x18000c730  mov     rcx, rdi; TokenHandle
0x18000c733  call    cs:__imp_NtQueryInformationToken
0x18000c73a  nop     dword ptr [rax+rax+00h]
0x18000c73f  test    eax, eax
0x18000c741  jns     short loc_18000C760
0x18000c743  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000c74a  mov     r8, rbx; P
0x18000c74d  xor     edx, edx; Flags
0x18000c74f  call    cs:__imp_RtlFreeHeap
0x18000c756  nop     dword ptr [rax+rax+00h]
0x18000c75b  jmp     loc_18000C6B6
0x18000c760  mov     rdx, [rbx]; Sid2
0x18000c763  mov     rcx, cs:Sid1; Sid1
0x18000c76a  call    cs:__imp_RtlEqualSid
0x18000c771  nop     dword ptr [rax+rax+00h]
0x18000c776  movzx   edi, al
0x18000c779  test    esi, esi
0x18000c77b  jz      short loc_18000C795
0x18000c77d  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000c784  mov     r8, rbx; P
0x18000c787  xor     edx, edx; Flags
0x18000c789  call    cs:__imp_RtlFreeHeap
0x18000c790  nop     dword ptr [rax+rax+00h]
0x18000c795  mov     eax, edi
0x18000c797  mov     rcx, [rbp+57h+var_20]
0x18000c79b  xor     rcx, rsp; StackCookie
0x18000c79e  call    __security_check_cookie
0x18000c7a3  lea     r11, [rsp+100h+var_10]
0x18000c7ab  mov     rbx, [r11+28h]
0x18000c7af  mov     rsi, [r11+30h]
0x18000c7b3  mov     rsp, r11
0x18000c7b6  pop     r14
0x18000c7b8  pop     rdi
0x18000c7b9  pop     rbp
0x18000c7ba  retn
```
