# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800a9300`
- end: `0x1800a9409`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `265`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800a9300`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a938f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a938f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a935d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a935d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a93cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a93d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a93cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a93d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a933a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a933a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a936d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a936d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a93c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a93c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x1800a9300  mov     [rsp-8+arg_0], rbx
0x1800a9305  push    rbp
0x1800a9306  mov     rbp, rsp
0x1800a9309  sub     rsp, 50h
0x1800a930d  mov     [rbp+var_18], 0
0x1800a9315  mov     [rbp+var_8], 0
0x1800a931d  lea     rax, [rbp+var_18]
0x1800a9321  mov     [rsp+50h+ppv], rax; ppv
0x1800a9326  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800a932d  xor     edx, edx; pUnkOuter
0x1800a932f  lea     r8d, [rdx+1]; dwClsContext
0x1800a9333  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800a933a  call    cs:__imp_CoCreateInstance
0x1800a9340  test    eax, eax
0x1800a9342  js      short loc_1800A935D
0x1800a9344  mov     rcx, [rbp+var_18]
0x1800a9348  mov     rax, [rcx]
0x1800a934b  lea     r8, [rbp+var_8]
0x1800a934f  mov     edx, 4
0x1800a9354  mov     rax, [rax+20h]
0x1800a9358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a935d  call    cs:__imp_GetCurrentProcessId
0x1800a9363  mov     r8d, eax; dwProcessId
0x1800a9366  xor     edx, edx; bInheritHandle
0x1800a9368  mov     ecx, 1000h; dwDesiredAccess
0x1800a936d  call    cs:__imp_OpenProcess
0x1800a9373  mov     rbx, rax
0x1800a9376  test    rax, rax
0x1800a9379  jz      short loc_1800A93DC
0x1800a937b  mov     [rbp+TokenHandle], 0
0x1800a9383  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a9387  mov     edx, 8; DesiredAccess
0x1800a938c  mov     rcx, rax; ProcessHandle
0x1800a938f  call    cs:__imp_OpenProcessToken
0x1800a9395  test    eax, eax
0x1800a9397  jz      short loc_1800A93D2
0x1800a9399  mov     [rbp+ReturnLength], 0
0x1800a93a0  mov     [rbp+TokenInformation], 0
0x1800a93a7  lea     rax, [rbp+ReturnLength]
0x1800a93ab  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800a93b0  mov     r9d, 4; TokenInformationLength
0x1800a93b6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800a93ba  lea     edx, [r9+19h]; TokenInformationClass
0x1800a93be  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a93c2  call    cs:__imp_GetTokenInformation
0x1800a93c8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a93cc  call    cs:__imp_CloseHandle
0x1800a93d2  mov     rcx, rbx; hObject
0x1800a93d5  call    cs:__imp_CloseHandle
0x1800a93db  nop
0x1800a93dc  mov     rcx, [rbp+var_18]
0x1800a93e0  test    rcx, rcx
0x1800a93e3  jz      short loc_1800A93F9
0x1800a93e5  mov     [rbp+var_18], 0
0x1800a93ed  mov     rdx, [rcx]
0x1800a93f0  mov     rax, [rdx+10h]
0x1800a93f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93f9  mov     eax, 1
0x1800a93fe  mov     rbx, [rsp+50h+arg_0]
0x1800a9403  add     rsp, 50h
0x1800a9407  pop     rbp
0x1800a9408  retn
```
