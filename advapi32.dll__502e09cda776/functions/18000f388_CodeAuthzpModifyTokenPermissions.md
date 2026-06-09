# CodeAuthzpModifyTokenPermissions

- ea: `0x18000f388`
- end: `0x18000f5a5`
- name: `CodeAuthzpModifyTokenPermissions`
- size: `541`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000fc88`

## callees

- `0x18000f388`
- `0x180072042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000f454`
- `ntdll!RtlLengthSid` at `0x18000f46d`
- `ntdll!RtlLengthSid` at `0x18000f454`
- `ntdll!RtlLengthSid` at `0x18000f46d`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000f4e6`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000f511`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000f4e6`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000f511`
- `ntdll!NtSetInformationToken` at `0x18000f53a`
- `ntdll!NtSetInformationToken` at `0x18000f53a`
- `ntdll!RtlFreeHeap` at `0x18000f560`
- `ntdll!RtlFreeHeap` at `0x18000f57e`
- `ntdll!RtlFreeHeap` at `0x18000f560`
- `ntdll!RtlFreeHeap` at `0x18000f57e`
- `ntdll!NtQueryInformationToken` at `0x18000f3c6`
- `ntdll!NtQueryInformationToken` at `0x18000f434`
- `ntdll!NtQueryInformationToken` at `0x18000f3c6`
- `ntdll!NtQueryInformationToken` at `0x18000f434`
- `ntdll!RtlAllocateHeap` at `0x18000f3f6`
- `ntdll!RtlAllocateHeap` at `0x18000f49a`
- `ntdll!RtlAllocateHeap` at `0x18000f3f6`
- `ntdll!RtlAllocateHeap` at `0x18000f49a`

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
0x18000f388  mov     rax, rsp
0x18000f38b  mov     [rax+18h], r8d
0x18000f38f  push    rbx
0x18000f390  push    rbp
0x18000f391  push    rsi
0x18000f392  push    rdi
0x18000f393  push    r14
0x18000f395  push    r15
0x18000f397  sub     rsp, 48h
0x18000f39b  mov     rbp, r9
0x18000f39e  mov     qword ptr [rax-48h], 0
0x18000f3a6  xor     r9d, r9d; TokenInformationLength
0x18000f3a9  mov     dword ptr [rax+18h], 0
0x18000f3b0  mov     r15, rdx
0x18000f3b3  lea     rax, [rax+18h]
0x18000f3b7  xor     r8d, r8d; TokenInformation
0x18000f3ba  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f3bf  mov     r14, rcx
0x18000f3c2  lea     edx, [r9+6]; TokenInformationClass
0x18000f3c6  call    cs:__imp_NtQueryInformationToken
0x18000f3cd  nop     dword ptr [rax+rax+00h]
0x18000f3d2  mov     ebx, eax
0x18000f3d4  cmp     eax, 0C0000023h
0x18000f3d9  jnz     loc_18000F58C
0x18000f3df  mov     rcx, gs:60h
0x18000f3e8  xor     edx, edx; Flags
0x18000f3ea  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18000f3f2  mov     rcx, [rcx+30h]; HeapHandle
0x18000f3f6  call    cs:__imp_RtlAllocateHeap
0x18000f3fd  nop     dword ptr [rax+rax+00h]
0x18000f402  mov     rsi, rax
0x18000f405  test    rax, rax
0x18000f408  jnz     short loc_18000F414
0x18000f40a  mov     ebx, 0C0000017h
0x18000f40f  jmp     loc_18000F595
0x18000f414  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x18000f41c  lea     rax, [rsp+78h+Size]
0x18000f424  mov     r8, rsi; TokenInformation
0x18000f427  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f42c  mov     edx, 6; TokenInformationClass
0x18000f431  mov     rcx, r14; TokenHandle
0x18000f434  call    cs:__imp_NtQueryInformationToken
0x18000f43b  nop     dword ptr [rax+rax+00h]
0x18000f440  mov     ebx, eax
0x18000f442  test    eax, eax
0x18000f444  js      loc_18000F56C
0x18000f44a  mov     rax, [rsi]
0x18000f44d  mov     rcx, r15; Sid
0x18000f450  movzx   ebx, word ptr [rax+2]
0x18000f454  call    cs:__imp_RtlLengthSid
0x18000f45b  nop     dword ptr [rax+rax+00h]
0x18000f460  add     ebx, 8
0x18000f463  add     ebx, eax
0x18000f465  test    rbp, rbp
0x18000f468  jz      short loc_18000F47E
0x18000f46a  mov     rcx, rbp; Sid
0x18000f46d  call    cs:__imp_RtlLengthSid
0x18000f474  nop     dword ptr [rax+rax+00h]
0x18000f479  add     ebx, 8
0x18000f47c  add     ebx, eax
0x18000f47e  mov     rcx, gs:60h
0x18000f487  mov     eax, 0FFFFh
0x18000f48c  cmp     ebx, eax
0x18000f48e  cmova   ebx, eax
0x18000f491  xor     edx, edx; Flags
0x18000f493  mov     rcx, [rcx+30h]; HeapHandle
0x18000f497  mov     r8d, ebx; Size
0x18000f49a  call    cs:__imp_RtlAllocateHeap
0x18000f4a1  nop     dword ptr [rax+rax+00h]
0x18000f4a6  mov     rdi, rax
0x18000f4a9  test    rax, rax
0x18000f4ac  jnz     short loc_18000F4B8
0x18000f4ae  mov     ebx, 0C0000017h
0x18000f4b3  jmp     loc_18000F56C
0x18000f4b8  mov     rdx, [rsi]; Src
0x18000f4bb  mov     rcx, rdi; void *
0x18000f4be  movzx   r8d, word ptr [rdx+2]; Size
0x18000f4c3  call    memcpy_0
0x18000f4c8  mov     edx, 2; dwAceRevision
0x18000f4cd  mov     [rsp+78h+ReturnLength], r15; pSid
0x18000f4d2  mov     r15d, 10000000h
0x18000f4d8  mov     [rdi+2], bx
0x18000f4dc  mov     r9d, r15d; AccessMask
0x18000f4df  mov     rcx, rdi; pAcl
0x18000f4e2  lea     r8d, [rdx+1]; AceFlags
0x18000f4e6  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000f4ed  nop     dword ptr [rax+rax+00h]
0x18000f4f2  mov     ebx, eax
0x18000f4f4  test    eax, eax
0x18000f4f6  js      short loc_18000F54E
0x18000f4f8  test    rbp, rbp
0x18000f4fb  jz      short loc_18000F523
0x18000f4fd  mov     edx, 2; dwAceRevision
0x18000f502  mov     [rsp+78h+ReturnLength], rbp; pSid
0x18000f507  mov     r9d, r15d; AccessMask
0x18000f50a  mov     rcx, rdi; pAcl
0x18000f50d  lea     r8d, [rdx+1]; AceFlags
0x18000f511  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000f518  nop     dword ptr [rax+rax+00h]
0x18000f51d  mov     ebx, eax
0x18000f51f  test    eax, eax
0x18000f521  js      short loc_18000F54E
0x18000f523  mov     r9d, 8; TokenInformationLength
0x18000f529  mov     [rsp+78h+TokenInformation], rdi
0x18000f52e  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x18000f533  mov     rcx, r14; TokenHandle
0x18000f536  lea     edx, [r9-2]; TokenInformationClass
0x18000f53a  call    cs:__imp_NtSetInformationToken
0x18000f541  nop     dword ptr [rax+rax+00h]
0x18000f546  mov     ebx, eax
0x18000f548  test    eax, eax
0x18000f54a  js      short loc_18000F54E
0x18000f54c  xor     ebx, ebx
0x18000f54e  mov     rcx, gs:60h
0x18000f557  mov     r8, rdi; P
0x18000f55a  xor     edx, edx; Flags
0x18000f55c  mov     rcx, [rcx+30h]; HeapHandle
0x18000f560  call    cs:__imp_RtlFreeHeap
0x18000f567  nop     dword ptr [rax+rax+00h]
0x18000f56c  mov     rcx, gs:60h
0x18000f575  mov     r8, rsi; P
0x18000f578  xor     edx, edx; Flags
0x18000f57a  mov     rcx, [rcx+30h]; HeapHandle
0x18000f57e  call    cs:__imp_RtlFreeHeap
0x18000f585  nop     dword ptr [rax+rax+00h]
0x18000f58a  jmp     short loc_18000F595
0x18000f58c  test    eax, eax
0x18000f58e  js      short loc_18000F595
0x18000f590  mov     ebx, 0C0000001h
0x18000f595  mov     eax, ebx
0x18000f597  add     rsp, 48h
0x18000f59b  pop     r15
0x18000f59d  pop     r14
0x18000f59f  pop     rdi
0x18000f5a0  pop     rsi
0x18000f5a1  pop     rbp
0x18000f5a2  pop     rbx
0x18000f5a3  retn
```
