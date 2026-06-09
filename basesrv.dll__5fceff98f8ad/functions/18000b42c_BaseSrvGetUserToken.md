# BaseSrvGetUserToken

- ea: `0x18000b42c`
- end: `0x18000b4f7`
- name: `BaseSrvGetUserToken`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008938`
- `0x18000bcf8`

## callees

- `0x18000b42c`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18000b4c5`
- `ntdll!NtOpenProcessToken` at `0x18000b4c5`
- `ntdll!NtOpenThreadToken` at `0x18000b494`
- `ntdll!NtOpenThreadToken` at `0x18000b494`
- `CSRSRV!CsrUnlockProcess` at `0x18000b4d8`
- `CSRSRV!CsrUnlockProcess` at `0x18000b4d8`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b451`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b451`
- `CSRSRV!CsrRevertToSelf` at `0x18000b4a2`
- `CSRSRV!CsrRevertToSelf` at `0x18000b4a2`
- `CSRSRV!CsrImpersonateClient` at `0x18000b467`
- `CSRSRV!CsrImpersonateClient` at `0x18000b467`

## pseudocode

```c
__int64 __fastcall BaseSrvGetUserToken(__int64 a1, int a2, void **a3)
{
  BOOL v4; // edi
  __int64 result; // rax
  unsigned int v6; // ebx
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v4 = a2 != 0;
  result = CsrLockProcessByClientId(a1, &v7);
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)CsrImpersonateClient(0) )
    {
      v6 = NtOpenThreadToken(*((HANDLE *)NtCurrentTeb()->CsrClientThread + 8), v4 + 8, 1u, a3);
      CsrRevertToSelf();
      if ( v6 == -1073741700 )
        v6 = NtOpenProcessToken(*(HANDLE *)(v7 + 80), v4 + 8, a3);
    }
    else
    {
      v6 = -1073741659;
    }
    CsrUnlockProcess(v7);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000b42c  mov     rax, rsp
0x18000b42f  mov     [rax+8], rbx
0x18000b433  mov     [rax+10h], rsi
0x18000b437  push    rdi
0x18000b438  sub     rsp, 20h
0x18000b43c  neg     edx
0x18000b43e  mov     qword ptr [rax+20h], 0
0x18000b446  lea     rdx, [rax+20h]
0x18000b44a  mov     rsi, r8
0x18000b44d  sbb     edi, edi
0x18000b44f  neg     edi
0x18000b451  call    cs:__imp_CsrLockProcessByClientId
0x18000b458  nop     dword ptr [rax+rax+00h]
0x18000b45d  test    eax, eax
0x18000b45f  js      loc_18000B4E6
0x18000b465  xor     ecx, ecx
0x18000b467  call    cs:__imp_CsrImpersonateClient
0x18000b46e  nop     dword ptr [rax+rax+00h]
0x18000b473  test    al, al
0x18000b475  jnz     short loc_18000B47E
0x18000b477  mov     ebx, 0C00000A5h
0x18000b47c  jmp     short loc_18000B4D3
0x18000b47e  mov     rcx, gs:70h
0x18000b487  lea     edx, [rdi+8]; DesiredAccess
0x18000b48a  mov     r9, rsi; TokenHandle
0x18000b48d  mov     r8b, 1; OpenAsSelf
0x18000b490  mov     rcx, [rcx+40h]; ThreadHandle
0x18000b494  call    cs:__imp_NtOpenThreadToken
0x18000b49b  nop     dword ptr [rax+rax+00h]
0x18000b4a0  mov     ebx, eax
0x18000b4a2  call    cs:__imp_CsrRevertToSelf
0x18000b4a9  nop     dword ptr [rax+rax+00h]
0x18000b4ae  cmp     ebx, 0C000007Ch
0x18000b4b4  jnz     short loc_18000B4D3
0x18000b4b6  mov     rcx, [rsp+28h+arg_18]
0x18000b4bb  lea     edx, [rdi+8]; DesiredAccess
0x18000b4be  mov     r8, rsi; TokenHandle
0x18000b4c1  mov     rcx, [rcx+50h]; ProcessHandle
0x18000b4c5  call    cs:__imp_NtOpenProcessToken
0x18000b4cc  nop     dword ptr [rax+rax+00h]
0x18000b4d1  mov     ebx, eax
0x18000b4d3  mov     rcx, [rsp+28h+arg_18]
0x18000b4d8  call    cs:__imp_CsrUnlockProcess
0x18000b4df  nop     dword ptr [rax+rax+00h]
0x18000b4e4  mov     eax, ebx
0x18000b4e6  mov     rbx, [rsp+28h+arg_0]
0x18000b4eb  mov     rsi, [rsp+28h+arg_8]
0x18000b4f0  add     rsp, 20h
0x18000b4f4  pop     rdi
0x18000b4f5  retn
```
