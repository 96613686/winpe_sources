# BaseSrvGetUserToken

- ea: `0x18000b18c`
- end: `0x18000b254`
- name: `BaseSrvGetUserToken`
- size: `200`
- prototype: `__int64 __fastcall(__int64, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008644`
- `0x18000ba38`

## callees

- `0x18000b18c`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18000b222`
- `ntdll!NtOpenProcessToken` at `0x18000b222`
- `ntdll!NtOpenThreadToken` at `0x18000b1f1`
- `ntdll!NtOpenThreadToken` at `0x18000b1f1`
- `CSRSRV!CsrUnlockProcess` at `0x18000b235`
- `CSRSRV!CsrUnlockProcess` at `0x18000b235`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b1ae`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b1ae`
- `CSRSRV!CsrRevertToSelf` at `0x18000b1ff`
- `CSRSRV!CsrRevertToSelf` at `0x18000b1ff`
- `CSRSRV!CsrImpersonateClient` at `0x18000b1c4`
- `CSRSRV!CsrImpersonateClient` at `0x18000b1c4`

## pseudocode

```c
__int64 __fastcall BaseSrvGetUserToken(__int64 a1, int a2, void **a3)
{
  BOOL v4; // edi
  __int64 result; // rax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v4 = a2 != 0;
  result = CsrLockProcessByClientId(a1, &v8);
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)CsrImpersonateClient(0) )
    {
      v6 = NtOpenThreadToken(*((HANDLE *)NtCurrentTeb()->CsrClientThread + 8), v4 + 8, 1u, a3);
      CsrRevertToSelf(v7);
      if ( v6 == -1073741700 )
        v6 = NtOpenProcessToken(*(HANDLE *)(v8 + 80), v4 + 8, a3);
    }
    else
    {
      v6 = -1073741659;
    }
    CsrUnlockProcess(v8);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000b18c  mov     rax, rsp
0x18000b18f  mov     [rax+8], rbx
0x18000b193  mov     [rax+10h], rsi
0x18000b197  push    rdi
0x18000b198  sub     rsp, 20h
0x18000b19c  and     qword ptr [rax+20h], 0
0x18000b1a1  mov     rsi, r8
0x18000b1a4  neg     edx
0x18000b1a6  lea     rdx, [rax+20h]
0x18000b1aa  sbb     edi, edi
0x18000b1ac  neg     edi
0x18000b1ae  call    cs:__imp_CsrLockProcessByClientId
0x18000b1b5  nop     dword ptr [rax+rax+00h]
0x18000b1ba  test    eax, eax
0x18000b1bc  js      loc_18000B243
0x18000b1c2  xor     ecx, ecx
0x18000b1c4  call    cs:__imp_CsrImpersonateClient
0x18000b1cb  nop     dword ptr [rax+rax+00h]
0x18000b1d0  test    al, al
0x18000b1d2  jnz     short loc_18000B1DB
0x18000b1d4  mov     ebx, 0C00000A5h
0x18000b1d9  jmp     short loc_18000B230
0x18000b1db  mov     rcx, gs:70h
0x18000b1e4  lea     edx, [rdi+8]; DesiredAccess
0x18000b1e7  mov     r9, rsi; TokenHandle
0x18000b1ea  mov     r8b, 1; OpenAsSelf
0x18000b1ed  mov     rcx, [rcx+40h]; ThreadHandle
0x18000b1f1  call    cs:__imp_NtOpenThreadToken
0x18000b1f8  nop     dword ptr [rax+rax+00h]
0x18000b1fd  mov     ebx, eax
0x18000b1ff  call    cs:__imp_CsrRevertToSelf
0x18000b206  nop     dword ptr [rax+rax+00h]
0x18000b20b  cmp     ebx, 0C000007Ch
0x18000b211  jnz     short loc_18000B230
0x18000b213  mov     rcx, [rsp+28h+arg_18]
0x18000b218  lea     edx, [rdi+8]; DesiredAccess
0x18000b21b  mov     r8, rsi; TokenHandle
0x18000b21e  mov     rcx, [rcx+50h]; ProcessHandle
0x18000b222  call    cs:__imp_NtOpenProcessToken
0x18000b229  nop     dword ptr [rax+rax+00h]
0x18000b22e  mov     ebx, eax
0x18000b230  mov     rcx, [rsp+28h+arg_18]
0x18000b235  call    cs:__imp_CsrUnlockProcess
0x18000b23c  nop     dword ptr [rax+rax+00h]
0x18000b241  mov     eax, ebx
0x18000b243  mov     rbx, [rsp+28h+arg_0]
0x18000b248  mov     rsi, [rsp+28h+arg_8]
0x18000b24d  add     rsp, 20h
0x18000b251  pop     rdi
0x18000b252  retn
```
