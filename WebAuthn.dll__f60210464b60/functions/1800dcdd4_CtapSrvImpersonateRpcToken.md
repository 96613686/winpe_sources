# CtapSrvImpersonateRpcToken

- ea: `0x1800dcdd4`
- end: `0x1800dce6e`
- name: `CtapSrvImpersonateRpcToken`
- size: `154`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180085a2c`
- `0x180088e6c`
- `0x180089b74`

## callees

- `0x18002bbf4`
- `0x1800dcdd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dce09`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dce09`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800dce2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800dce2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcdf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcdf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dce4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dce4a`

## pseudocode

```c
__int64 __fastcall CtapSrvImpersonateRpcToken(HANDLE Token, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // eax
  void *v6; // rcx
  unsigned int v7; // ebx
  unsigned int NonzeroLastError; // eax
  __int64 result; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
    || (v5 = _GetNonzeroLastError(), v6 = 0, v7 = v5, TokenHandle = 0, v5 == 1008) )
  {
    v7 = 0;
    if ( SetThreadToken(0, Token) )
    {
      v6 = TokenHandle;
    }
    else
    {
      NonzeroLastError = _GetNonzeroLastError();
      v6 = TokenHandle;
      v7 = NonzeroLastError;
      if ( TokenHandle )
      {
        CloseHandle(TokenHandle);
        v6 = 0;
      }
    }
  }
  result = v7;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800dcdd4  mov     [rsp+arg_0], rbx
0x1800dcdd9  mov     [rsp+arg_10], rsi
0x1800dcdde  push    rdi
0x1800dcddf  sub     rsp, 20h
0x1800dcde3  mov     rdi, rdx
0x1800dcde6  mov     [rsp+28h+TokenHandle], 0
0x1800dcdef  mov     rsi, rcx
0x1800dcdf2  call    cs:__imp_GetCurrentThread
0x1800dcdf8  mov     edx, 0Ch; DesiredAccess
0x1800dcdfd  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800dce02  mov     rcx, rax; ThreadHandle
0x1800dce05  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800dce09  call    cs:__imp_OpenThreadToken
0x1800dce0f  test    eax, eax
0x1800dce11  jnz     short loc_1800DCE28
0x1800dce13  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dce18  xor     ecx, ecx
0x1800dce1a  mov     ebx, eax
0x1800dce1c  mov     [rsp+28h+TokenHandle], rcx
0x1800dce21  cmp     eax, 3F0h
0x1800dce26  jnz     short loc_1800DCE59
0x1800dce28  mov     rdx, rsi; Token
0x1800dce2b  xor     ecx, ecx; Thread
0x1800dce2d  xor     ebx, ebx
0x1800dce2f  call    cs:__imp_SetThreadToken
0x1800dce35  test    eax, eax
0x1800dce37  jnz     short loc_1800DCE54
0x1800dce39  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dce3e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800dce43  mov     ebx, eax
0x1800dce45  test    rcx, rcx
0x1800dce48  jz      short loc_1800DCE59
0x1800dce4a  call    cs:__imp_CloseHandle
0x1800dce50  xor     ecx, ecx
0x1800dce52  jmp     short loc_1800DCE59
0x1800dce54  mov     rcx, [rsp+28h+TokenHandle]
0x1800dce59  mov     rsi, [rsp+28h+arg_10]
0x1800dce5e  mov     eax, ebx
0x1800dce60  mov     rbx, [rsp+28h+arg_0]
0x1800dce65  mov     [rdi], rcx
0x1800dce68  add     rsp, 20h
0x1800dce6c  pop     rdi
0x1800dce6d  retn
```
