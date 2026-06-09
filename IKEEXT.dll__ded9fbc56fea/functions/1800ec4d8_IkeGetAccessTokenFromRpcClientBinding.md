# IkeGetAccessTokenFromRpcClientBinding

- ea: `0x1800ec4d8`
- end: `0x1800ec5c5`
- name: `IkeGetAccessTokenFromRpcClientBinding`
- size: `237`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800ec7c4`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ec4d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ec556`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ec556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ec53f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ec53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec560`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec58a`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec58a`
- `RPCRT4!RpcImpersonateClient` at `0x1800ec51b`
- `RPCRT4!RpcImpersonateClient` at `0x1800ec51b`

## string_xrefs

- `0x1800ec52b`: `RpcImpersonateClient`
- `0x1800ec505`: `IkeGetAccessTokenFromRpcClientBinding`
- `0x1800ec592`: `IkeGetAccessTokenFromRpcClientBinding`
- `0x1800ec59e`: `IkeGetAccessTokenFromRpcClientBinding`
- `0x1800ec56c`: `OpenThreadToken`

## pseudocode

```c
__int64 __fastcall IkeGetAccessTokenFromRpcClientBinding(RPC_BINDING_HANDLE BindingHandle, void **a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v9; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  TraceLogHelper("IkeGetAccessTokenFromRpcClientBinding", 1);
  *a2 = 0;
  v4 = RpcImpersonateClient(BindingHandle);
  if ( v4 )
  {
    v6 = WfpReportSysErrorAsWinError(v5, "RpcImpersonateClient", v4, 1);
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
      v6 = WfpReportSysErrorAsWinError(v9, "OpenThreadToken", LastError, 1);
    }
    RpcRevertToSelf();
  }
  TraceLogHelper("IkeGetAccessTokenFromRpcClientBinding", 0);
  return IkeReturnError(v6, "IkeGetAccessTokenFromRpcClientBinding");
}

```

## disassembly

```asm
0x1800ec4d8  mov     [rsp+arg_10], rbx
0x1800ec4dd  push    rdi
0x1800ec4de  sub     rsp, 30h
0x1800ec4e2  mov     rax, cs:__security_cookie
0x1800ec4e9  xor     rax, rsp
0x1800ec4ec  mov     [rsp+38h+var_10], rax
0x1800ec4f1  mov     rdi, rdx
0x1800ec4f4  mov     [rsp+38h+TokenHandle], 0
0x1800ec4fd  mov     rbx, rcx
0x1800ec500  mov     edx, 1
0x1800ec505  lea     rcx, aIkegetaccessto; "IkeGetAccessTokenFromRpcClientBinding"
0x1800ec50c  call    TraceLogHelper
0x1800ec511  mov     rcx, rbx; BindingHandle
0x1800ec514  mov     qword ptr [rdi], 0
0x1800ec51b  call    cs:__imp_RpcImpersonateClient
0x1800ec521  test    eax, eax
0x1800ec523  jz      short loc_1800EC53F
0x1800ec525  mov     r9d, 1
0x1800ec52b  lea     rdx, aRpcimpersonate; "RpcImpersonateClient"
0x1800ec532  mov     r8d, eax
0x1800ec535  call    WfpReportSysErrorAsWinError
0x1800ec53a  mov     rbx, rax
0x1800ec53d  jmp     short loc_1800EC590
0x1800ec53f  call    cs:__imp_GetCurrentThread
0x1800ec545  mov     edx, 8; DesiredAccess
0x1800ec54a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ec54f  mov     rcx, rax; ThreadHandle
0x1800ec552  lea     r8d, [rdx-7]; OpenAsSelf
0x1800ec556  call    cs:__imp_OpenThreadToken
0x1800ec55c  test    eax, eax
0x1800ec55e  jnz     short loc_1800EC580
0x1800ec560  call    cs:__imp_GetLastError
0x1800ec566  mov     r9d, 1
0x1800ec56c  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x1800ec573  mov     r8d, eax
0x1800ec576  call    WfpReportSysErrorAsWinError
0x1800ec57b  mov     rbx, rax
0x1800ec57e  jmp     short loc_1800EC58A
0x1800ec580  mov     rax, [rsp+38h+TokenHandle]
0x1800ec585  xor     ebx, ebx
0x1800ec587  mov     [rdi], rax
0x1800ec58a  call    cs:__imp_RpcRevertToSelf
0x1800ec590  xor     edx, edx
0x1800ec592  lea     rcx, aIkegetaccessto; "IkeGetAccessTokenFromRpcClientBinding"
0x1800ec599  call    TraceLogHelper
0x1800ec59e  lea     rdx, aIkegetaccessto; "IkeGetAccessTokenFromRpcClientBinding"
0x1800ec5a5  mov     rcx, rbx
0x1800ec5a8  call    IkeReturnError
0x1800ec5ad  mov     rcx, [rsp+38h+var_10]
0x1800ec5b2  xor     rcx, rsp; StackCookie
0x1800ec5b5  call    __security_check_cookie
0x1800ec5ba  mov     rbx, [rsp+38h+arg_10]
0x1800ec5bf  add     rsp, 30h
0x1800ec5c3  pop     rdi
0x1800ec5c4  retn
```
