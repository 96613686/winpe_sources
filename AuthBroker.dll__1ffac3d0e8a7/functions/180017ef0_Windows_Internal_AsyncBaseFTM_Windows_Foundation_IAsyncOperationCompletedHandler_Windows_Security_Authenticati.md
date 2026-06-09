# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180017ef0`
- end: `0x180017ff8`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(_RTL_RUN_ONCE *__formal, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180017ef0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017f4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017f7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017f7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fc5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017fb2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017fb2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017f5d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017f5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017f2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017f2a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        _RTL_RUN_ONCE *__formal,
        void *a2,
        void **a3)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  IGlobalOptions *ptr; // rcx
  unsigned int uIsAppContainer; // [rsp+30h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IGlobalOptions> globalOptions; // [rsp+38h] [rbp-18h] BYREF
  void *hToken; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 value; // [rsp+48h] [rbp-8h] BYREF
  unsigned int cbToken; // [rsp+78h] [rbp+28h] BYREF

  globalOptions.ptr_ = 0;
  value = 0;
  if ( CoCreateInstance(
         &CLSID_GlobalOptions,
         0,
         1u,
         &GUID_0000015b_0000_0000_c000_000000000046,
         (LPVOID *)&globalOptions.ptr_) >= 0 )
    globalOptions.ptr_->Query(globalOptions.ptr_, COMGLB_RO_SETTINGS, &value);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    hToken = 0;
    if ( OpenProcessToken(v4, 8u, &hToken) )
    {
      cbToken = 0;
      uIsAppContainer = 0;
      GetTokenInformation(hToken, TokenIsAppContainer, &uIsAppContainer, 4u, &cbToken);
      CloseHandle(hToken);
    }
    CloseHandle(v5);
  }
  ptr = globalOptions.ptr_;
  if ( globalOptions.ptr_ )
  {
    globalOptions.ptr_ = 0;
    ptr->Release(ptr);
  }
  return 1;
}

```

## disassembly

```asm
0x180017ef0  mov     [rsp-8+arg_0], rbx
0x180017ef5  push    rbp
0x180017ef6  mov     rbp, rsp
0x180017ef9  sub     rsp, 50h
0x180017efd  xor     edx, edx; pUnkOuter
0x180017eff  mov     [rbp+globalOptions.ptr_], 0
0x180017f07  lea     rax, [rbp+globalOptions]
0x180017f0b  mov     [rbp+value], 0
0x180017f13  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180017f1a  mov     [rsp+50h+ppv], rax; ppv
0x180017f1f  lea     __formal, CLSID_GlobalOptions; rclsid
0x180017f26  lea     r8d, [rdx+1]; dwClsContext
0x180017f2a  call    cs:__imp_CoCreateInstance
0x180017f30  test    eax, eax
0x180017f32  js      short loc_180017F4D
0x180017f34  mov     __formal, [rbp+globalOptions.ptr_]
0x180017f38  lea     r8, [rbp+value]
0x180017f3c  mov     edx, 4
0x180017f41  mov     rax, [__formal]
0x180017f44  mov     rax, [rax+20h]
0x180017f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f4d  call    cs:__imp_GetCurrentProcessId
0x180017f53  xor     edx, edx; bInheritHandle
0x180017f55  mov     ecx, 1000h; dwDesiredAccess
0x180017f5a  mov     r8d, eax; dwProcessId
0x180017f5d  call    cs:__imp_OpenProcess
0x180017f63  mov     rbx, rax
0x180017f66  test    rax, rax
0x180017f69  jz      short loc_180017FCB
0x180017f6b  lea     r8, [rbp+hToken]; TokenHandle
0x180017f6f  mov     [rbp+hToken], 0
0x180017f77  mov     edx, 8; DesiredAccess
0x180017f7c  mov     __formal, rax; ProcessHandle
0x180017f7f  call    cs:__imp_OpenProcessToken
0x180017f85  test    eax, eax
0x180017f87  jz      short loc_180017FC2
0x180017f89  mov     __formal, [rbp+hToken]; TokenHandle
0x180017f8d  lea     rax, [rbp+cbToken]
0x180017f91  mov     r9d, 4; TokenInformationLength
0x180017f97  mov     [rbp+cbToken], 0
0x180017f9e  lea     r8, [rbp+uIsAppContainer]; TokenInformation
0x180017fa2  mov     [rbp+uIsAppContainer], 0
0x180017fa9  mov     [rsp+50h+ppv], rax; ReturnLength
0x180017fae  lea     edx, [r9+19h]; TokenInformationClass
0x180017fb2  call    cs:__imp_GetTokenInformation
0x180017fb8  mov     __formal, [rbp+hToken]; hObject
0x180017fbc  call    cs:__imp_CloseHandle
0x180017fc2  mov     __formal, rbx; hObject
0x180017fc5  call    cs:__imp_CloseHandle
0x180017fcb  mov     __formal, [rbp+globalOptions.ptr_]
0x180017fcf  test    __formal, __formal
0x180017fd2  jz      short loc_180017FE8
0x180017fd4  mov     [rbp+globalOptions.ptr_], 0
0x180017fdc  mov     rdx, [__formal]
0x180017fdf  mov     rax, [rdx+10h]
0x180017fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe8  mov     rbx, [rsp+50h+arg_0]
0x180017fed  mov     eax, 1
0x180017ff2  add     rsp, 50h
0x180017ff6  pop     rbp
0x180017ff7  retn
```
