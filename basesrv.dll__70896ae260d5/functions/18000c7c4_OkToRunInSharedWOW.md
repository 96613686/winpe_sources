# OkToRunInSharedWOW

- ea: `0x18000c7c4`
- end: `0x18000c8e7`
- name: `OkToRunInSharedWOW`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008d80`

## callees

- `0x18000c61c`
- `0x18000c7c4`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000c849`
- `ntdll!NtClose` at `0x18000c849`
- `ntdll!NtOpenProcessToken` at `0x18000c808`
- `ntdll!NtOpenProcessToken` at `0x18000c808`
- `ntdll!NtOpenThreadToken` at `0x18000c88a`
- `ntdll!NtOpenThreadToken` at `0x18000c88a`
- `CSRSRV!CsrUnlockProcess` at `0x18000c8c8`
- `CSRSRV!CsrUnlockProcess` at `0x18000c8c8`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c7e3`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000c7e3`
- `CSRSRV!CsrRevertToSelf` at `0x18000c898`
- `CSRSRV!CsrRevertToSelf` at `0x18000c898`
- `CSRSRV!CsrImpersonateClient` at `0x18000c85b`
- `CSRSRV!CsrImpersonateClient` at `0x18000c85b`

## pseudocode

```c
__int64 __fastcall OkToRunInSharedWOW(__int64 a1, __int64 a2, void **a3)
{
  __int64 result; // rax
  NTSTATUS v6; // ebx
  NTSTATUS v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  result = CsrLockProcessByClientId(a1, &v9);
  if ( (int)result >= 0 )
  {
    v6 = NtOpenProcessToken(*(HANDLE *)(v9 + 80), 8u, a3);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(void *, __int64))UserTestTokenForInteractive)(*a3, a2);
      if ( v6 < 0 )
      {
        if ( (unsigned int)IsClientSystem(*a3) )
        {
          NtClose(*a3);
          *a3 = 0;
          if ( (unsigned __int8)CsrImpersonateClient(0) )
          {
            v7 = NtOpenThreadToken(*((HANDLE *)NtCurrentTeb()->CsrClientThread + 8), 8u, 1u, a3);
            CsrRevertToSelf(v8);
            if ( v7 < 0 )
              v6 = -1073741790;
            else
              v6 = ((__int64 (__fastcall *)(void *, __int64))UserTestTokenForInteractive)(*a3, a2);
          }
          else
          {
            v6 = -1073741659;
          }
        }
      }
    }
    CsrUnlockProcess(v9);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000c7c4  mov     rax, rsp
0x18000c7c7  mov     [rax+8], rbx
0x18000c7cb  mov     [rax+10h], rsi
0x18000c7cf  push    rdi
0x18000c7d0  sub     rsp, 20h
0x18000c7d4  and     qword ptr [rax+20h], 0
0x18000c7d9  mov     rsi, rdx
0x18000c7dc  lea     rdx, [rax+20h]
0x18000c7e0  mov     rdi, r8
0x18000c7e3  call    cs:__imp_CsrLockProcessByClientId
0x18000c7ea  nop     dword ptr [rax+rax+00h]
0x18000c7ef  test    eax, eax
0x18000c7f1  js      loc_18000C8D6
0x18000c7f7  mov     rcx, [rsp+28h+arg_18]
0x18000c7fc  mov     r8, rdi; TokenHandle
0x18000c7ff  mov     edx, 8; DesiredAccess
0x18000c804  mov     rcx, [rcx+50h]; ProcessHandle
0x18000c808  call    cs:__imp_NtOpenProcessToken
0x18000c80f  nop     dword ptr [rax+rax+00h]
0x18000c814  mov     ebx, eax
0x18000c816  test    eax, eax
0x18000c818  js      loc_18000C8C3
0x18000c81e  mov     rcx, [rdi]
0x18000c821  mov     rdx, rsi
0x18000c824  mov     rax, cs:UserTestTokenForInteractive
0x18000c82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c830  mov     ebx, eax
0x18000c832  test    eax, eax
0x18000c834  jns     loc_18000C8C3
0x18000c83a  mov     rcx, [rdi]; TokenHandle
0x18000c83d  call    IsClientSystem
0x18000c842  test    eax, eax
0x18000c844  jz      short loc_18000C8C3
0x18000c846  mov     rcx, [rdi]; Handle
0x18000c849  call    cs:__imp_NtClose
0x18000c850  nop     dword ptr [rax+rax+00h]
0x18000c855  and     qword ptr [rdi], 0
0x18000c859  xor     ecx, ecx
0x18000c85b  call    cs:__imp_CsrImpersonateClient
0x18000c862  nop     dword ptr [rax+rax+00h]
0x18000c867  test    al, al
0x18000c869  jnz     short loc_18000C872
0x18000c86b  mov     ebx, 0C00000A5h
0x18000c870  jmp     short loc_18000C8C3
0x18000c872  mov     rcx, gs:70h
0x18000c87b  mov     r9, rdi; TokenHandle
0x18000c87e  mov     r8b, 1; OpenAsSelf
0x18000c881  mov     edx, 8; DesiredAccess
0x18000c886  mov     rcx, [rcx+40h]; ThreadHandle
0x18000c88a  call    cs:__imp_NtOpenThreadToken
0x18000c891  nop     dword ptr [rax+rax+00h]
0x18000c896  mov     ebx, eax
0x18000c898  call    cs:__imp_CsrRevertToSelf
0x18000c89f  nop     dword ptr [rax+rax+00h]
0x18000c8a4  test    ebx, ebx
0x18000c8a6  js      short loc_18000C8BE
0x18000c8a8  mov     rcx, [rdi]
0x18000c8ab  mov     rdx, rsi
0x18000c8ae  mov     rax, cs:UserTestTokenForInteractive
0x18000c8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ba  mov     ebx, eax
0x18000c8bc  jmp     short loc_18000C8C3
0x18000c8be  mov     ebx, 0C0000022h
0x18000c8c3  mov     rcx, [rsp+28h+arg_18]
0x18000c8c8  call    cs:__imp_CsrUnlockProcess
0x18000c8cf  nop     dword ptr [rax+rax+00h]
0x18000c8d4  mov     eax, ebx
0x18000c8d6  mov     rbx, [rsp+28h+arg_0]
0x18000c8db  mov     rsi, [rsp+28h+arg_8]
0x18000c8e0  add     rsp, 20h
0x18000c8e4  pop     rdi
0x18000c8e5  retn
```
