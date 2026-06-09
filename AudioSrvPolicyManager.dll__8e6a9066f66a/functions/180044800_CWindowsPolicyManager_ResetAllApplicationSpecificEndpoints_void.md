# CWindowsPolicyManager::ResetAllApplicationSpecificEndpoints(void *)

- ea: `0x180044800`
- end: `0x18004494d`
- name: `?ResetAllApplicationSpecificEndpoints@CWindowsPolicyManager@@UEAAJPEAX@Z`
- size: `333`
- prototype: `int(CWindowsPolicyManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000a080`
- `0x18000a384`
- `0x18000f040`
- `0x180012844`
- `0x18001d8a0`
- `0x18002acfc`
- `0x18002df70`
- `0x180044800`
- `0x1800469b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004488d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004488d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180044876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180044876`
- `RPCRT4!RpcRevertToSelf` at `0x1800448fc`
- `RPCRT4!RpcRevertToSelf` at `0x180044904`
- `RPCRT4!RpcRevertToSelf` at `0x1800448fc`
- `RPCRT4!RpcRevertToSelf` at `0x180044904`
- `RPCRT4!RpcImpersonateClient` at `0x180044839`
- `RPCRT4!RpcImpersonateClient` at `0x180044839`

## pseudocode

```c
__int64 __fastcall CWindowsPolicyManager::ResetAllApplicationSpecificEndpoints(CWindowsPolicyManager *this, void *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  unsigned int LastError; // eax
  unsigned int TokenInformation; // eax
  CApplicationManager *v11; // rcx
  int v12; // eax
  unsigned int v13; // [rsp+20h] [rbp-18h]
  unsigned int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v16; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v3 = ApplicationSpecificEndpointInfo::ClearAllPersistedApplicationDefaultEndpoints();
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = RpcImpersonateClient(a2);
    if ( v5 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x19E,
               (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
               (const char *)v5,
               v13);
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v16 = 0;
      TokenInformation = GetTokenInformation(TokenHandle, 0, 0, 0, &v16);
      if ( !TokenInformation )
      {
        RpcRevertToSelf();
        v12 = CApplicationManager::ResetAllApplicationSpecificEndpoints(v11, v16);
        v4 = v12;
        if ( v12 >= 0 )
          v4 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
            (const char *)(unsigned int)v12,
            v14);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return v4;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x1A6,
                    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
                    (const char *)TokenInformation,
                    v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1A2,
                    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
                    v8);
    }
    v4 = LastError;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)v3,
      v13);
  }
  return v4;
}

```

## disassembly

```asm
0x180044800  mov     [rsp+arg_0], rbx
0x180044805  push    rdi
0x180044806  sub     rsp, 30h
0x18004480a  mov     rdi, rdx
0x18004480d  call    ?ClearAllPersistedApplicationDefaultEndpoints@ApplicationSpecificEndpointInfo@@SAJXZ; ApplicationSpecificEndpointInfo::ClearAllPersistedApplicationDefaultEndpoints(void)
0x180044812  mov     ebx, eax
0x180044814  test    eax, eax
0x180044816  jns     short loc_180044836
0x180044818  mov     rcx, [rsp+38h]; this
0x18004481d  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044824  mov     r9d, eax; char *
0x180044827  mov     edx, 19Bh; void *
0x18004482c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044831  jmp     loc_180044940
0x180044836  mov     rcx, rdi; BindingHandle
0x180044839  call    cs:__imp_RpcImpersonateClient
0x18004483f  test    eax, eax
0x180044841  jz      short loc_180044861
0x180044843  mov     rcx, [rsp+38h]; this
0x180044848  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x18004484f  mov     r9d, eax; char *
0x180044852  mov     edx, 19Eh; void *
0x180044857  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004485c  jmp     loc_180044942
0x180044861  xor     edx, edx
0x180044863  mov     [rsp+38h+TokenHandle], 0
0x18004486c  lea     rcx, [rsp+38h+TokenHandle]
0x180044871  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044876  call    cs:__imp_GetCurrentThread
0x18004487c  mov     edx, 8; DesiredAccess
0x180044881  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180044886  mov     rcx, rax; ThreadHandle
0x180044889  lea     r8d, [rdx-7]; OpenAsSelf
0x18004488d  call    cs:__imp_OpenThreadToken
0x180044893  test    eax, eax
0x180044895  jnz     short loc_1800448AF
0x180044897  mov     rcx, [rsp+38h]; this
0x18004489c  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800448a3  mov     edx, 1A2h; void *
0x1800448a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800448ad  jmp     short loc_1800448F0
0x1800448af  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800448b4  lea     rax, [rsp+38h+arg_10]
0x1800448b9  xor     r9d, r9d; unsigned __int16 **
0x1800448bc  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800448c1  xor     r8d, r8d; unsigned int *
0x1800448c4  mov     [rsp+38h+arg_10], 0
0x1800448cc  xor     edx, edx; unsigned __int16 **
0x1800448ce  call    ?GetTokenInformation@@YAKPEAXPEAPEAGPEAK12@Z; GetTokenInformation(void *,ushort * *,ulong *,ushort * *,ulong *)
0x1800448d3  test    eax, eax
0x1800448d5  jz      short loc_180044904
0x1800448d7  mov     rcx, [rsp+38h]; this
0x1800448dc  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800448e3  mov     r9d, eax; char *
0x1800448e6  mov     edx, 1A6h; void *
0x1800448eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800448f0  lea     rcx, [rsp+38h+TokenHandle]
0x1800448f5  mov     ebx, eax
0x1800448f7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800448fc  call    cs:__imp_RpcRevertToSelf
0x180044902  jmp     short loc_180044940
0x180044904  call    cs:__imp_RpcRevertToSelf
0x18004490a  mov     edx, [rsp+38h+arg_10]; unsigned int
0x18004490e  call    ?ResetAllApplicationSpecificEndpoints@CApplicationManager@@QEAAJK@Z; CApplicationManager::ResetAllApplicationSpecificEndpoints(ulong)
0x180044913  mov     ebx, eax
0x180044915  test    eax, eax
0x180044917  jns     short loc_180044934
0x180044919  mov     rcx, [rsp+38h]; this
0x18004491e  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044925  mov     r9d, eax; char *
0x180044928  mov     edx, 1ABh; void *
0x18004492d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044932  jmp     short loc_180044936
0x180044934  xor     ebx, ebx
0x180044936  lea     rcx, [rsp+38h+TokenHandle]
0x18004493b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180044940  mov     eax, ebx
0x180044942  mov     rbx, [rsp+38h+arg_0]
0x180044947  add     rsp, 30h
0x18004494b  pop     rdi
0x18004494c  retn
```
