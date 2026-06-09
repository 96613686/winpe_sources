# BfeRpcGetAccessTokenFromClientBinding

- ea: `0x180039e30`
- end: `0x180039ef6`
- name: `BfeRpcGetAccessTokenFromClientBinding`
- size: `198`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18004aeb8`
- `0x180071148`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180039e30`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ecb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039e7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039e7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039e66`
- `RPCRT4!RpcImpersonateClient` at `0x180039e5c`
- `RPCRT4!RpcImpersonateClient` at `0x180039e5c`
- `RPCRT4!RpcRevertToSelf` at `0x180039e91`
- `RPCRT4!RpcRevertToSelf` at `0x180039e91`

## string_xrefs

- `0x180039eba`: `RpcImpersonateClient`
- `0x180039ed4`: `OpenThreadToken`
- `0x180039ee5`: `BfeRpcGetAccessTokenFromClientBinding`

## pseudocode

```c
__int64 __fastcall BfeRpcGetAccessTokenFromClientBinding(void *a1, void **a2)
{
  unsigned int v3; // eax
  __int64 v4; // rcx
  HANDLE CurrentThread; // rax
  __int64 v6; // rbx
  DWORD LastError; // eax
  __int64 v9; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  *a2 = 0;
  v3 = RpcImpersonateClient(a1);
  if ( v3 )
  {
    v6 = WfpReportSysErrorAsWinError(v4, "RpcImpersonateClient", v3);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v6 = 0;
      *a2 = TokenHandle;
    }
    else
    {
      LastError = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v9, "OpenThreadToken", LastError);
    }
    RpcRevertToSelf();
  }
  if ( v6 )
    WfpReportError(v6, "BfeRpcGetAccessTokenFromClientBinding");
  return v6;
}

```

## disassembly

```asm
0x180039e30  mov     [rsp+arg_10], rbx
0x180039e35  push    rdi
0x180039e36  sub     rsp, 30h
0x180039e3a  mov     rax, cs:__security_cookie
0x180039e41  xor     rax, rsp
0x180039e44  mov     [rsp+38h+var_10], rax
0x180039e49  mov     rdi, rdx
0x180039e4c  mov     [rsp+38h+TokenHandle], 0
0x180039e55  mov     qword ptr [rdx], 0
0x180039e5c  call    cs:__imp_RpcImpersonateClient
0x180039e62  test    eax, eax
0x180039e64  jnz     short loc_180039EB7
0x180039e66  call    cs:__imp_GetCurrentThread
0x180039e6c  mov     edx, 8; DesiredAccess
0x180039e71  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180039e76  mov     rcx, rax; ThreadHandle
0x180039e79  lea     r8d, [rdx-7]; OpenAsSelf
0x180039e7d  call    cs:__imp_OpenThreadToken
0x180039e83  test    eax, eax
0x180039e85  jz      short loc_180039ECB
0x180039e87  mov     rax, [rsp+38h+TokenHandle]
0x180039e8c  xor     ebx, ebx
0x180039e8e  mov     [rdi], rax
0x180039e91  call    cs:__imp_RpcRevertToSelf
0x180039e97  test    rbx, rbx
0x180039e9a  jnz     short loc_180039EE5
0x180039e9c  mov     rax, rbx
0x180039e9f  mov     rcx, [rsp+38h+var_10]
0x180039ea4  xor     rcx, rsp; StackCookie
0x180039ea7  call    __security_check_cookie
0x180039eac  mov     rbx, [rsp+38h+arg_10]
0x180039eb1  add     rsp, 30h
0x180039eb5  pop     rdi
0x180039eb6  retn
0x180039eb7  mov     r8d, eax
0x180039eba  lea     rdx, aRpcimpersonate; "RpcImpersonateClient"
0x180039ec1  call    WfpReportSysErrorAsWinError
0x180039ec6  mov     rbx, rax
0x180039ec9  jmp     short loc_180039E97
0x180039ecb  call    cs:__imp_GetLastError
0x180039ed1  mov     r8d, eax
0x180039ed4  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x180039edb  call    WfpReportSysErrorAsWinError
0x180039ee0  mov     rbx, rax
0x180039ee3  jmp     short loc_180039E91
0x180039ee5  lea     rdx, aBferpcgetacces; "BfeRpcGetAccessTokenFromClientBinding"
0x180039eec  mov     rcx, rbx
0x180039eef  call    WfpReportError
0x180039ef4  jmp     short loc_180039E9C
```
