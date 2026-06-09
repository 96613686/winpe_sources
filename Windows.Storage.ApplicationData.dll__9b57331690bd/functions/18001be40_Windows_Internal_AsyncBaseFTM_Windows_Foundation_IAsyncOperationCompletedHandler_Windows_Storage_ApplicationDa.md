# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18001be40`
- end: `0x18001bf48`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(_RTL_RUN_ONCE *__formal, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001be40`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001be9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001be9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001becf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001becf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001bead`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001bead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bf02`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bf02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001be7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001be7a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18001be40  mov     [rsp-8+arg_0], rbx
0x18001be45  push    rbp
0x18001be46  mov     rbp, rsp
0x18001be49  sub     rsp, 50h
0x18001be4d  xor     edx, edx; pUnkOuter
0x18001be4f  mov     [rbp+globalOptions.ptr_], 0
0x18001be57  lea     rax, [rbp+globalOptions]
0x18001be5b  mov     [rbp+value], 0
0x18001be63  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001be6a  mov     [rsp+50h+ppv], rax; ppv
0x18001be6f  lea     __formal, CLSID_GlobalOptions; rclsid
0x18001be76  lea     r8d, [rdx+1]; dwClsContext
0x18001be7a  call    cs:__imp_CoCreateInstance
0x18001be80  test    eax, eax
0x18001be82  js      short loc_18001BE9D
0x18001be84  mov     __formal, [rbp+globalOptions.ptr_]
0x18001be88  lea     r8, [rbp+value]
0x18001be8c  mov     edx, 4
0x18001be91  mov     rax, [__formal]
0x18001be94  mov     rax, [rax+20h]
0x18001be98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be9d  call    cs:__imp_GetCurrentProcessId
0x18001bea3  xor     edx, edx; bInheritHandle
0x18001bea5  mov     ecx, 1000h; dwDesiredAccess
0x18001beaa  mov     r8d, eax; dwProcessId
0x18001bead  call    cs:__imp_OpenProcess
0x18001beb3  mov     rbx, rax
0x18001beb6  test    rax, rax
0x18001beb9  jz      short loc_18001BF1B
0x18001bebb  lea     r8, [rbp+hToken]; TokenHandle
0x18001bebf  mov     [rbp+hToken], 0
0x18001bec7  mov     edx, 8; DesiredAccess
0x18001becc  mov     __formal, rax; ProcessHandle
0x18001becf  call    cs:__imp_OpenProcessToken
0x18001bed5  test    eax, eax
0x18001bed7  jz      short loc_18001BF12
0x18001bed9  mov     __formal, [rbp+hToken]; TokenHandle
0x18001bedd  lea     rax, [rbp+cbToken]
0x18001bee1  mov     r9d, 4; TokenInformationLength
0x18001bee7  mov     [rbp+cbToken], 0
0x18001beee  lea     r8, [rbp+uIsAppContainer]; TokenInformation
0x18001bef2  mov     [rbp+uIsAppContainer], 0
0x18001bef9  mov     [rsp+50h+ppv], rax; ReturnLength
0x18001befe  lea     edx, [r9+19h]; TokenInformationClass
0x18001bf02  call    cs:__imp_GetTokenInformation
0x18001bf08  mov     __formal, [rbp+hToken]; hObject
0x18001bf0c  call    cs:__imp_CloseHandle
0x18001bf12  mov     __formal, rbx; hObject
0x18001bf15  call    cs:__imp_CloseHandle
0x18001bf1b  mov     __formal, [rbp+globalOptions.ptr_]
0x18001bf1f  test    __formal, __formal
0x18001bf22  jz      short loc_18001BF38
0x18001bf24  mov     [rbp+globalOptions.ptr_], 0
0x18001bf2c  mov     rdx, [__formal]
0x18001bf2f  mov     rax, [rdx+10h]
0x18001bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf38  mov     rbx, [rsp+50h+arg_0]
0x18001bf3d  mov     eax, 1
0x18001bf42  add     rsp, 50h
0x18001bf46  pop     rbp
0x18001bf47  retn
```
