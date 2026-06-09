# GetCallerToken

- ea: `0x180024e90`
- end: `0x180024fb7`
- name: `GetCallerToken`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e1f0`
- `0x1800aab28`

## callees

- `0x180024e90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024f34`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024f34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024f21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024f21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024eca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024fa1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180024f6c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180024f6c`
- `RPCRT4!RpcRevertToSelf` at `0x180024fac`
- `RPCRT4!RpcRevertToSelf` at `0x180024fac`
- `RPCRT4!RpcImpersonateClient` at `0x180024ef8`
- `RPCRT4!RpcImpersonateClient` at `0x180024ef8`

## pseudocode

```c
RPC_STATUS __fastcall GetCallerToken(void *a1, int a2, _QWORD *a3)
{
  int v3; // edi
  HANDLE CurrentThread; // rax
  void *v6; // rax
  DWORD LastError; // ebx
  RPC_STATUS result; // eax
  HANDLE CurrentProcess; // rax
  void *phNewToken; // [rsp+30h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  if ( a2 )
  {
    result = RpcImpersonateClient(a1);
    if ( result )
    {
      if ( result != 1725 )
        return result;
    }
    else
    {
      v3 = 1;
    }
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
      {
        phNewToken = 0;
        if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, &phNewToken) )
        {
          CloseHandle(TokenHandle);
          v6 = phNewToken;
          goto LABEL_4;
        }
      }
      LastError = GetLastError();
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_5;
  }
  v6 = TokenHandle;
LABEL_4:
  *a3 = v6;
  LastError = 0;
LABEL_5:
  if ( v3 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180024e90  mov     [rsp+arg_8], rsi
0x180024e95  push    rdi
0x180024e96  sub     rsp, 40h
0x180024e9a  xor     edi, edi
0x180024e9c  mov     rsi, r8
0x180024e9f  test    edx, edx
0x180024ea1  jnz     short loc_180024EF8
0x180024ea3  mov     [rsp+48h+arg_0], rbx
0x180024ea8  mov     [rsp+48h+TokenHandle], 0
0x180024eb1  call    cs:__imp_GetCurrentThread
0x180024eb7  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180024ebc  mov     edx, 8; DesiredAccess
0x180024ec1  mov     rcx, rax; ThreadHandle
0x180024ec4  mov     r8d, 1; OpenAsSelf
0x180024eca  call    cs:__imp_OpenThreadToken
0x180024ed0  test    eax, eax
0x180024ed2  jz      short loc_180024F12
0x180024ed4  mov     rax, [rsp+48h+TokenHandle]
0x180024ed9  mov     [rsi], rax
0x180024edc  xor     ebx, ebx
0x180024ede  test    edi, edi
0x180024ee0  jnz     loc_180024FAC
0x180024ee6  mov     eax, ebx
0x180024ee8  mov     rbx, [rsp+48h+arg_0]
0x180024eed  mov     rsi, [rsp+48h+arg_8]
0x180024ef2  add     rsp, 40h
0x180024ef6  pop     rdi
0x180024ef7  retn
0x180024ef8  call    cs:__imp_RpcImpersonateClient
0x180024efe  test    eax, eax
0x180024f00  jnz     short loc_180024F09
0x180024f02  mov     edi, 1
0x180024f07  jmp     short loc_180024EA3
0x180024f09  cmp     eax, 6BDh
0x180024f0e  jnz     short loc_180024EED
0x180024f10  jmp     short loc_180024EA3
0x180024f12  call    cs:__imp_GetLastError
0x180024f18  mov     ebx, eax
0x180024f1a  cmp     eax, 3F0h
0x180024f1f  jnz     short loc_180024F93
0x180024f21  call    cs:__imp_GetCurrentProcess
0x180024f27  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180024f2c  mov     edx, 0Ah; DesiredAccess
0x180024f31  mov     rcx, rax; ProcessHandle
0x180024f34  call    cs:__imp_OpenProcessToken
0x180024f3a  test    eax, eax
0x180024f3c  jz      short loc_180024F8B
0x180024f3e  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x180024f43  lea     rax, [rsp+48h+var_18]
0x180024f48  mov     [rsp+48h+phNewToken], rax; phNewToken
0x180024f4d  mov     r9d, 1; ImpersonationLevel
0x180024f53  xor     r8d, r8d; lpTokenAttributes
0x180024f56  mov     [rsp+48h+TokenType], 2; TokenType
0x180024f5e  mov     edx, 2000000h; dwDesiredAccess
0x180024f63  mov     [rsp+48h+var_18], 0
0x180024f6c  call    cs:__imp_DuplicateTokenEx
0x180024f72  test    eax, eax
0x180024f74  jz      short loc_180024F8B
0x180024f76  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180024f7b  call    cs:__imp_CloseHandle
0x180024f81  mov     rax, [rsp+48h+var_18]
0x180024f86  jmp     loc_180024ED9
0x180024f8b  call    cs:__imp_GetLastError
0x180024f91  mov     ebx, eax
0x180024f93  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180024f98  test    rcx, rcx
0x180024f9b  jz      loc_180024EDE
0x180024fa1  call    cs:__imp_CloseHandle
0x180024fa7  jmp     loc_180024EDE
0x180024fac  call    cs:__imp_RpcRevertToSelf
0x180024fb2  jmp     loc_180024EE6
```
