# CodeAuthzpModifyTokenPermissions

- ea: `0x180009f70`
- end: `0x18000a14a`
- name: `CodeAuthzpModifyTokenPermissions`
- size: `474`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a78c`

## callees

- `0x180009f70`
- `0x180065042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000a02a`
- `ntdll!RtlLengthSid` at `0x18000a03d`
- `ntdll!RtlLengthSid` at `0x18000a02a`
- `ntdll!RtlLengthSid` at `0x18000a03d`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000a0aa`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000a0cf`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000a0aa`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000a0cf`
- `ntdll!NtSetInformationToken` at `0x18000a0f2`
- `ntdll!NtSetInformationToken` at `0x18000a0f2`
- `ntdll!RtlFreeHeap` at `0x18000a112`
- `ntdll!RtlFreeHeap` at `0x18000a12a`
- `ntdll!RtlFreeHeap` at `0x18000a112`
- `ntdll!RtlFreeHeap` at `0x18000a12a`
- `ntdll!NtQueryInformationToken` at `0x180009fae`
- `ntdll!NtQueryInformationToken` at `0x18000a010`
- `ntdll!NtQueryInformationToken` at `0x180009fae`
- `ntdll!NtQueryInformationToken` at `0x18000a010`
- `ntdll!RtlAllocateHeap` at `0x180009fd8`
- `ntdll!RtlAllocateHeap` at `0x18000a064`
- `ntdll!RtlAllocateHeap` at `0x180009fd8`
- `ntdll!RtlAllocateHeap` at `0x18000a064`

## pseudocode

```c
__int64 __fastcall CodeAuthzpModifyTokenPermissions(HANDLE TokenHandle, PSID pSid, __int64 a3, void *a4)
{
  NTSTATUS InformationToken; // eax
  NTSTATUS v8; // ebx
  PVOID Heap; // rsi
  int v10; // ebx
  ULONG v11; // ebx
  struct _PEB *v12; // rcx
  ACL *v13; // rax
  ACL *v14; // rdi
  ACL *TokenInformation; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T Size; // [rsp+90h] [rbp+18h] BYREF

  TokenInformation = 0;
  LODWORD(Size) = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, 0, 0, (PULONG)&Size);
  v8 = InformationToken;
  if ( InformationToken == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    if ( Heap )
    {
      v8 = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, Heap, Size, (PULONG)&Size);
      if ( v8 >= 0 )
      {
        v10 = *(unsigned __int16 *)(*(_QWORD *)Heap + 2LL);
        v11 = RtlLengthSid(pSid) + v10 + 8;
        if ( a4 )
          v11 += RtlLengthSid(a4) + 8;
        v12 = NtCurrentPeb();
        if ( v11 > 0xFFFF )
          v11 = 0xFFFF;
        v13 = (ACL *)RtlAllocateHeap(v12->ProcessHeap, 0, v11);
        v14 = v13;
        if ( v13 )
        {
          memcpy_0(v13, *(const void **)Heap, *(unsigned __int16 *)(*(_QWORD *)Heap + 2LL));
          v14->AclSize = v11;
          v8 = RtlAddAccessAllowedAceEx(v14, 2u, 3u, 0x10000000u, pSid);
          if ( v8 >= 0 )
          {
            if ( !a4 || (v8 = RtlAddAccessAllowedAceEx(v14, 2u, 3u, 0x10000000u, a4), v8 >= 0) )
            {
              TokenInformation = v14;
              v8 = NtSetInformationToken(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u);
              if ( v8 >= 0 )
                v8 = 0;
            }
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
        }
        else
        {
          v8 = -1073741801;
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else if ( InformationToken >= 0 )
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009f70  mov     rax, rsp
0x180009f73  mov     [rax+18h], r8d
0x180009f77  push    rbx
0x180009f78  push    rbp
0x180009f79  push    rsi
0x180009f7a  push    rdi
0x180009f7b  push    r14
0x180009f7d  push    r15
0x180009f7f  sub     rsp, 48h
0x180009f83  mov     rbp, r9
0x180009f86  mov     qword ptr [rax-48h], 0
0x180009f8e  xor     r9d, r9d; TokenInformationLength
0x180009f91  mov     dword ptr [rax+18h], 0
0x180009f98  mov     r15, rdx
0x180009f9b  lea     rax, [rax+18h]
0x180009f9f  xor     r8d, r8d; TokenInformation
0x180009fa2  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180009fa7  mov     r14, rcx
0x180009faa  lea     edx, [r9+6]; TokenInformationClass
0x180009fae  call    cs:__imp_NtQueryInformationToken
0x180009fb4  mov     ebx, eax
0x180009fb6  cmp     eax, 0C0000023h
0x180009fbb  jnz     loc_18000A132
0x180009fc1  mov     rcx, gs:60h
0x180009fca  xor     edx, edx; Flags
0x180009fcc  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180009fd4  mov     rcx, [rcx+30h]; HeapHandle
0x180009fd8  call    cs:__imp_RtlAllocateHeap
0x180009fde  mov     rsi, rax
0x180009fe1  test    rax, rax
0x180009fe4  jnz     short loc_180009FF0
0x180009fe6  mov     ebx, 0C0000017h
0x180009feb  jmp     loc_18000A13B
0x180009ff0  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x180009ff8  lea     rax, [rsp+78h+Size]
0x18000a000  mov     r8, rsi; TokenInformation
0x18000a003  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000a008  mov     edx, 6; TokenInformationClass
0x18000a00d  mov     rcx, r14; TokenHandle
0x18000a010  call    cs:__imp_NtQueryInformationToken
0x18000a016  mov     ebx, eax
0x18000a018  test    eax, eax
0x18000a01a  js      loc_18000A118
0x18000a020  mov     rax, [rsi]
0x18000a023  mov     rcx, r15; Sid
0x18000a026  movzx   ebx, word ptr [rax+2]
0x18000a02a  call    cs:__imp_RtlLengthSid
0x18000a030  add     ebx, 8
0x18000a033  add     ebx, eax
0x18000a035  test    rbp, rbp
0x18000a038  jz      short loc_18000A048
0x18000a03a  mov     rcx, rbp; Sid
0x18000a03d  call    cs:__imp_RtlLengthSid
0x18000a043  add     ebx, 8
0x18000a046  add     ebx, eax
0x18000a048  mov     rcx, gs:60h
0x18000a051  mov     eax, 0FFFFh
0x18000a056  cmp     ebx, eax
0x18000a058  cmova   ebx, eax
0x18000a05b  xor     edx, edx; Flags
0x18000a05d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a061  mov     r8d, ebx; Size
0x18000a064  call    cs:__imp_RtlAllocateHeap
0x18000a06a  mov     rdi, rax
0x18000a06d  test    rax, rax
0x18000a070  jnz     short loc_18000A07C
0x18000a072  mov     ebx, 0C0000017h
0x18000a077  jmp     loc_18000A118
0x18000a07c  mov     rdx, [rsi]; Src
0x18000a07f  mov     rcx, rdi; void *
0x18000a082  movzx   r8d, word ptr [rdx+2]; Size
0x18000a087  call    memcpy_0
0x18000a08c  mov     edx, 2; dwAceRevision
0x18000a091  mov     [rsp+78h+ReturnLength], r15; pSid
0x18000a096  mov     r15d, 10000000h
0x18000a09c  mov     [rdi+2], bx
0x18000a0a0  mov     r9d, r15d; AccessMask
0x18000a0a3  mov     rcx, rdi; pAcl
0x18000a0a6  lea     r8d, [rdx+1]; AceFlags
0x18000a0aa  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000a0b0  mov     ebx, eax
0x18000a0b2  test    eax, eax
0x18000a0b4  js      short loc_18000A100
0x18000a0b6  test    rbp, rbp
0x18000a0b9  jz      short loc_18000A0DB
0x18000a0bb  mov     edx, 2; dwAceRevision
0x18000a0c0  mov     [rsp+78h+ReturnLength], rbp; pSid
0x18000a0c5  mov     r9d, r15d; AccessMask
0x18000a0c8  mov     rcx, rdi; pAcl
0x18000a0cb  lea     r8d, [rdx+1]; AceFlags
0x18000a0cf  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000a0d5  mov     ebx, eax
0x18000a0d7  test    eax, eax
0x18000a0d9  js      short loc_18000A100
0x18000a0db  mov     r9d, 8; TokenInformationLength
0x18000a0e1  mov     [rsp+78h+TokenInformation], rdi
0x18000a0e6  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x18000a0eb  mov     rcx, r14; TokenHandle
0x18000a0ee  lea     edx, [r9-2]; TokenInformationClass
0x18000a0f2  call    cs:__imp_NtSetInformationToken
0x18000a0f8  mov     ebx, eax
0x18000a0fa  test    eax, eax
0x18000a0fc  js      short loc_18000A100
0x18000a0fe  xor     ebx, ebx
0x18000a100  mov     rcx, gs:60h
0x18000a109  mov     r8, rdi; P
0x18000a10c  xor     edx, edx; Flags
0x18000a10e  mov     rcx, [rcx+30h]; HeapHandle
0x18000a112  call    cs:__imp_RtlFreeHeap
0x18000a118  mov     rcx, gs:60h
0x18000a121  mov     r8, rsi; P
0x18000a124  xor     edx, edx; Flags
0x18000a126  mov     rcx, [rcx+30h]; HeapHandle
0x18000a12a  call    cs:__imp_RtlFreeHeap
0x18000a130  jmp     short loc_18000A13B
0x18000a132  test    eax, eax
0x18000a134  js      short loc_18000A13B
0x18000a136  mov     ebx, 0C0000001h
0x18000a13b  mov     eax, ebx
0x18000a13d  add     rsp, 48h
0x18000a141  pop     r15
0x18000a143  pop     r14
0x18000a145  pop     rdi
0x18000a146  pop     rsi
0x18000a147  pop     rbp
0x18000a148  pop     rbx
0x18000a149  retn
```
