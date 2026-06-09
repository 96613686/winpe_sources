# AccessCheck(void *)

- ea: `0x18010e4c0`
- end: `0x18010e578`
- name: `?AccessCheck@@YAJPEAX@Z`
- size: `184`
- prototype: `RPC_STATUS __fastcall(void *)`
- caller_count: `16`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180119560`
- `0x1801196e0`
- `0x18011aa90`
- `0x18011abb0`
- `0x18011ad50`
- `0x18011aeb0`
- `0x18011b080`
- `0x18011b1b0`
- `0x18011b3b0`
- `0x18011b5d0`
- `0x18011b800`
- `0x18011ba30`
- `0x18011bc50`
- `0x18011be80`
- `0x18011c190`
- `0x18011c350`

## callees

- `0x1800117bc`
- `0x180058630`
- `0x1800a1878`
- `0x18010e4c0`
- `0x18010ef28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010e519`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010e519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e502`
- `RPCRT4!RpcImpersonateClient` at `0x18010e4d4`
- `RPCRT4!RpcImpersonateClient` at `0x18010e4d4`
- `RPCRT4!RpcRevertToSelf` at `0x18010e56a`
- `RPCRT4!RpcRevertToSelf` at `0x18010e56a`

## string_xrefs

- `0x18010e528`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
RPC_STATUS __fastcall AccessCheck(void *a1)
{
  int LastError; // ebx
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v6; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  LastError = 0;
  if ( !a1 )
    return 0;
  result = RpcImpersonateClient(a1);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v6 = 0;
      if ( (int)CheckThreadAdmin(TokenHandle, &v6) < 0 || v6 != 1 )
        LastError = -2147024891;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x216,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                    v4);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18010e4c0  push    rbx
0x18010e4c2  sub     rsp, 20h
0x18010e4c6  xor     ebx, ebx
0x18010e4c8  test    rcx, rcx
0x18010e4cb  jnz     short loc_18010E4D4
0x18010e4cd  xor     eax, eax
0x18010e4cf  jmp     loc_18010E572
0x18010e4d4  call    cs:__imp_RpcImpersonateClient
0x18010e4da  test    eax, eax
0x18010e4dc  jz      short loc_18010E4F1
0x18010e4de  jle     loc_18010E572
0x18010e4e4  movzx   eax, ax
0x18010e4e7  or      eax, 80070000h
0x18010e4ec  jmp     loc_18010E572
0x18010e4f1  xor     edx, edx
0x18010e4f3  mov     [rsp+28h+TokenHandle], rbx
0x18010e4f8  lea     rcx, [rsp+28h+TokenHandle]
0x18010e4fd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18010e502  call    cs:__imp_GetCurrentThread
0x18010e508  mov     edx, 8; DesiredAccess
0x18010e50d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18010e512  mov     rcx, rax; ThreadHandle
0x18010e515  lea     r8d, [rdx-7]; OpenAsSelf
0x18010e519  call    cs:__imp_OpenThreadToken
0x18010e51f  test    eax, eax
0x18010e521  jnz     short loc_18010E53D
0x18010e523  mov     rcx, [rsp+28h]; this
0x18010e528  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010e52f  mov     edx, 216h; void *
0x18010e534  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010e539  mov     ebx, eax
0x18010e53b  jmp     short loc_18010E560
0x18010e53d  mov     rcx, [rsp+28h+TokenHandle]
0x18010e542  lea     rdx, [rsp+28h+arg_0]
0x18010e547  mov     [rsp+28h+arg_0], ebx
0x18010e54b  call    CheckThreadAdmin
0x18010e550  test    eax, eax
0x18010e552  js      short loc_18010E55B
0x18010e554  cmp     [rsp+28h+arg_0], 1
0x18010e559  jz      short loc_18010E560
0x18010e55b  mov     ebx, 80070005h
0x18010e560  lea     rcx, [rsp+28h+TokenHandle]
0x18010e565  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010e56a  call    cs:__imp_RpcRevertToSelf
0x18010e570  mov     eax, ebx
0x18010e572  add     rsp, 20h
0x18010e576  pop     rbx
0x18010e577  retn
```
