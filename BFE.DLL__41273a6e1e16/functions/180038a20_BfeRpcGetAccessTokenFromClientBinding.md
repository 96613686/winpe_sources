# BfeRpcGetAccessTokenFromClientBinding

- ea: `0x180038a20`
- end: `0x180038b05`
- name: `BfeRpcGetAccessTokenFromClientBinding`
- size: `229`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18004cce8`
- `0x18007391c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180038a20`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ad4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038a79`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038a5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038a5c`
- `RPCRT4!RpcImpersonateClient` at `0x180038a4c`
- `RPCRT4!RpcImpersonateClient` at `0x180038a4c`
- `RPCRT4!RpcRevertToSelf` at `0x180038a93`
- `RPCRT4!RpcRevertToSelf` at `0x180038a93`

## string_xrefs

- `0x180038ac3`: `RpcImpersonateClient`
- `0x180038ae3`: `OpenThreadToken`
- `0x180038af4`: `BfeRpcGetAccessTokenFromClientBinding`

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
0x180038a20  mov     [rsp+arg_10], rbx
0x180038a25  push    rdi
0x180038a26  sub     rsp, 30h
0x180038a2a  mov     rax, cs:__security_cookie
0x180038a31  xor     rax, rsp
0x180038a34  mov     [rsp+38h+var_10], rax
0x180038a39  mov     rdi, rdx
0x180038a3c  mov     [rsp+38h+TokenHandle], 0
0x180038a45  mov     qword ptr [rdx], 0
0x180038a4c  call    cs:__imp_RpcImpersonateClient
0x180038a53  nop     dword ptr [rax+rax+00h]
0x180038a58  test    eax, eax
0x180038a5a  jnz     short loc_180038AC0
0x180038a5c  call    cs:__imp_GetCurrentThread
0x180038a63  nop     dword ptr [rax+rax+00h]
0x180038a68  mov     edx, 8; DesiredAccess
0x180038a6d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180038a72  mov     rcx, rax; ThreadHandle
0x180038a75  lea     r8d, [rdx-7]; OpenAsSelf
0x180038a79  call    cs:__imp_OpenThreadToken
0x180038a80  nop     dword ptr [rax+rax+00h]
0x180038a85  test    eax, eax
0x180038a87  jz      short loc_180038AD4
0x180038a89  mov     rax, [rsp+38h+TokenHandle]
0x180038a8e  xor     ebx, ebx
0x180038a90  mov     [rdi], rax
0x180038a93  call    cs:__imp_RpcRevertToSelf
0x180038a9a  nop     dword ptr [rax+rax+00h]
0x180038a9f  test    rbx, rbx
0x180038aa2  jnz     short loc_180038AF4
0x180038aa4  mov     rax, rbx
0x180038aa7  mov     rcx, [rsp+38h+var_10]
0x180038aac  xor     rcx, rsp; StackCookie
0x180038aaf  call    __security_check_cookie
0x180038ab4  mov     rbx, [rsp+38h+arg_10]
0x180038ab9  add     rsp, 30h
0x180038abd  pop     rdi
0x180038abe  retn
0x180038ac0  mov     r8d, eax
0x180038ac3  lea     rdx, aRpcimpersonate; "RpcImpersonateClient"
0x180038aca  call    WfpReportSysErrorAsWinError
0x180038acf  mov     rbx, rax
0x180038ad2  jmp     short loc_180038A9F
0x180038ad4  call    cs:__imp_GetLastError
0x180038adb  nop     dword ptr [rax+rax+00h]
0x180038ae0  mov     r8d, eax
0x180038ae3  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x180038aea  call    WfpReportSysErrorAsWinError
0x180038aef  mov     rbx, rax
0x180038af2  jmp     short loc_180038A93
0x180038af4  lea     rdx, aBferpcgetacces; "BfeRpcGetAccessTokenFromClientBinding"
0x180038afb  mov     rcx, rbx
0x180038afe  call    WfpReportError
0x180038b03  jmp     short loc_180038AA4
```
