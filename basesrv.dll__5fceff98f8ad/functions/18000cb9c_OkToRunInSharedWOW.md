# OkToRunInSharedWOW

- ea: `0x18000cb9c`
- end: `0x18000ccc9`
- name: `OkToRunInSharedWOW`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000905c`

## callees

- `0x18000c9f8`
- `0x18000cb9c`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000cc28`
- `ntdll!NtClose` at `0x18000cc28`
- `ntdll!NtOpenProcessToken` at `0x18000cbe3`
- `ntdll!NtOpenProcessToken` at `0x18000cbe3`
- `ntdll!NtOpenThreadToken` at `0x18000cc6c`
- `ntdll!NtOpenThreadToken` at `0x18000cc6c`
- `CSRSRV!CsrUnlockProcess` at `0x18000ccaa`
- `CSRSRV!CsrUnlockProcess` at `0x18000ccaa`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000cbbe`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000cbbe`
- `CSRSRV!CsrRevertToSelf` at `0x18000cc7a`
- `CSRSRV!CsrRevertToSelf` at `0x18000cc7a`
- `CSRSRV!CsrImpersonateClient` at `0x18000cc3d`
- `CSRSRV!CsrImpersonateClient` at `0x18000cc3d`

## pseudocode

```c
__int64 __fastcall OkToRunInSharedWOW(__int64 a1, __int64 a2, void **a3)
{
  __int64 result; // rax
  NTSTATUS v6; // ebx
  NTSTATUS v7; // ebx
  __int64 v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  result = CsrLockProcessByClientId(a1, &v8);
  if ( (int)result >= 0 )
  {
    v6 = NtOpenProcessToken(*(HANDLE *)(v8 + 80), 8u, a3);
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
            CsrRevertToSelf();
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
    CsrUnlockProcess(v8);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000cb9c  mov     rax, rsp
0x18000cb9f  mov     [rax+8], rbx
0x18000cba3  mov     [rax+10h], rsi
0x18000cba7  push    rdi
0x18000cba8  sub     rsp, 20h
0x18000cbac  mov     rsi, rdx
0x18000cbaf  mov     qword ptr [rax+20h], 0
0x18000cbb7  lea     rdx, [rax+20h]
0x18000cbbb  mov     rdi, r8
0x18000cbbe  call    cs:__imp_CsrLockProcessByClientId
0x18000cbc5  nop     dword ptr [rax+rax+00h]
0x18000cbca  test    eax, eax
0x18000cbcc  js      loc_18000CCB8
0x18000cbd2  mov     rcx, [rsp+28h+arg_18]
0x18000cbd7  mov     r8, rdi; TokenHandle
0x18000cbda  mov     edx, 8; DesiredAccess
0x18000cbdf  mov     rcx, [rcx+50h]; ProcessHandle
0x18000cbe3  call    cs:__imp_NtOpenProcessToken
0x18000cbea  nop     dword ptr [rax+rax+00h]
0x18000cbef  mov     ebx, eax
0x18000cbf1  test    eax, eax
0x18000cbf3  js      loc_18000CCA5
0x18000cbf9  mov     rcx, [rdi]
0x18000cbfc  mov     rdx, rsi
0x18000cbff  mov     rax, cs:UserTestTokenForInteractive
0x18000cc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc0b  mov     ebx, eax
0x18000cc0d  test    eax, eax
0x18000cc0f  jns     loc_18000CCA5
0x18000cc15  mov     rcx, [rdi]; TokenHandle
0x18000cc18  call    IsClientSystem
0x18000cc1d  test    eax, eax
0x18000cc1f  jz      loc_18000CCA5
0x18000cc25  mov     rcx, [rdi]; Handle
0x18000cc28  call    cs:__imp_NtClose
0x18000cc2f  nop     dword ptr [rax+rax+00h]
0x18000cc34  xor     ecx, ecx
0x18000cc36  mov     qword ptr [rdi], 0
0x18000cc3d  call    cs:__imp_CsrImpersonateClient
0x18000cc44  nop     dword ptr [rax+rax+00h]
0x18000cc49  test    al, al
0x18000cc4b  jnz     short loc_18000CC54
0x18000cc4d  mov     ebx, 0C00000A5h
0x18000cc52  jmp     short loc_18000CCA5
0x18000cc54  mov     rcx, gs:70h
0x18000cc5d  mov     r9, rdi; TokenHandle
0x18000cc60  mov     r8b, 1; OpenAsSelf
0x18000cc63  mov     edx, 8; DesiredAccess
0x18000cc68  mov     rcx, [rcx+40h]; ThreadHandle
0x18000cc6c  call    cs:__imp_NtOpenThreadToken
0x18000cc73  nop     dword ptr [rax+rax+00h]
0x18000cc78  mov     ebx, eax
0x18000cc7a  call    cs:__imp_CsrRevertToSelf
0x18000cc81  nop     dword ptr [rax+rax+00h]
0x18000cc86  test    ebx, ebx
0x18000cc88  js      short loc_18000CCA0
0x18000cc8a  mov     rcx, [rdi]
0x18000cc8d  mov     rdx, rsi
0x18000cc90  mov     rax, cs:UserTestTokenForInteractive
0x18000cc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc9c  mov     ebx, eax
0x18000cc9e  jmp     short loc_18000CCA5
0x18000cca0  mov     ebx, 0C0000022h
0x18000cca5  mov     rcx, [rsp+28h+arg_18]
0x18000ccaa  call    cs:__imp_CsrUnlockProcess
0x18000ccb1  nop     dword ptr [rax+rax+00h]
0x18000ccb6  mov     eax, ebx
0x18000ccb8  mov     rbx, [rsp+28h+arg_0]
0x18000ccbd  mov     rsi, [rsp+28h+arg_8]
0x18000ccc2  add     rsp, 20h
0x18000ccc6  pop     rdi
0x18000ccc7  retn
```
