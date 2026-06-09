# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002d530`
- end: `0x18002d638`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `264`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002d530`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d5bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d5bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d58d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d605`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d56a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d56a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d59d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d59d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d5f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d5f2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  LPVOID v6; // rcx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v11 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v11);
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1000u, 0, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      CloseHandle(TokenHandle);
    }
    CloseHandle(v5);
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18002d530  mov     [rsp-8+arg_0], rbx
0x18002d535  push    rbp
0x18002d536  mov     rbp, rsp
0x18002d539  sub     rsp, 50h
0x18002d53d  xor     edx, edx; pUnkOuter
0x18002d53f  mov     [rbp+var_18], 0
0x18002d547  lea     rax, [rbp+var_18]
0x18002d54b  mov     [rbp+var_8], 0
0x18002d553  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002d55a  mov     [rsp+50h+ppv], rax; ppv
0x18002d55f  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002d566  lea     r8d, [rdx+1]; dwClsContext
0x18002d56a  call    cs:__imp_CoCreateInstance
0x18002d570  test    eax, eax
0x18002d572  js      short loc_18002D58D
0x18002d574  mov     rcx, [rbp+var_18]
0x18002d578  lea     r8, [rbp+var_8]
0x18002d57c  mov     edx, 4
0x18002d581  mov     rax, [rcx]
0x18002d584  mov     rax, [rax+20h]
0x18002d588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d58d  call    cs:__imp_GetCurrentProcessId
0x18002d593  xor     edx, edx; bInheritHandle
0x18002d595  mov     ecx, 1000h; dwDesiredAccess
0x18002d59a  mov     r8d, eax; dwProcessId
0x18002d59d  call    cs:__imp_OpenProcess
0x18002d5a3  mov     rbx, rax
0x18002d5a6  test    rax, rax
0x18002d5a9  jz      short loc_18002D60B
0x18002d5ab  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002d5af  mov     [rbp+TokenHandle], 0
0x18002d5b7  mov     edx, 8; DesiredAccess
0x18002d5bc  mov     rcx, rax; ProcessHandle
0x18002d5bf  call    cs:__imp_OpenProcessToken
0x18002d5c5  test    eax, eax
0x18002d5c7  jz      short loc_18002D602
0x18002d5c9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002d5cd  lea     rax, [rbp+ReturnLength]
0x18002d5d1  mov     r9d, 4; TokenInformationLength
0x18002d5d7  mov     [rbp+ReturnLength], 0
0x18002d5de  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002d5e2  mov     [rbp+TokenInformation], 0
0x18002d5e9  mov     [rsp+50h+ppv], rax; ReturnLength
0x18002d5ee  lea     edx, [r9+19h]; TokenInformationClass
0x18002d5f2  call    cs:__imp_GetTokenInformation
0x18002d5f8  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d5fc  call    cs:__imp_CloseHandle
0x18002d602  mov     rcx, rbx; hObject
0x18002d605  call    cs:__imp_CloseHandle
0x18002d60b  mov     rcx, [rbp+var_18]
0x18002d60f  test    rcx, rcx
0x18002d612  jz      short loc_18002D628
0x18002d614  mov     [rbp+var_18], 0
0x18002d61c  mov     rdx, [rcx]
0x18002d61f  mov     rax, [rdx+10h]
0x18002d623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d628  mov     rbx, [rsp+50h+arg_0]
0x18002d62d  mov     eax, 1
0x18002d632  add     rsp, 50h
0x18002d636  pop     rbp
0x18002d637  retn
```
