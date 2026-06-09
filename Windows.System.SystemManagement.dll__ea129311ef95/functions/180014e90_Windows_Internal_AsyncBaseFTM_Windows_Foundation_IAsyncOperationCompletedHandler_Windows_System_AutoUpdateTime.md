# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180014e90`
- end: `0x180014f9a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180014e90`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014eed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014f1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014f1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f65`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014eca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014eca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014efd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014efd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014f52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014f52`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
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
0x180014e90  mov     [rsp-8+arg_0], rbx
0x180014e95  push    rbp
0x180014e96  mov     rbp, rsp
0x180014e99  sub     rsp, 50h
0x180014e9d  mov     [rbp+var_18], 0
0x180014ea5  mov     [rbp+var_8], 0
0x180014ead  lea     rax, [rbp+var_18]
0x180014eb1  mov     [rsp+50h+ppv], rax; ppv
0x180014eb6  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180014ebd  xor     edx, edx; pUnkOuter
0x180014ebf  lea     r8d, [rdx+1]; dwClsContext
0x180014ec3  lea     rcx, CLSID_GlobalOptions; rclsid
0x180014eca  call    cs:__imp_CoCreateInstance
0x180014ed0  test    eax, eax
0x180014ed2  js      short loc_180014EED
0x180014ed4  mov     rcx, [rbp+var_18]
0x180014ed8  mov     rax, [rcx]
0x180014edb  lea     r8, [rbp+var_8]
0x180014edf  mov     edx, 4
0x180014ee4  mov     rax, [rax+20h]
0x180014ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eed  call    cs:__imp_GetCurrentProcessId
0x180014ef3  mov     r8d, eax; dwProcessId
0x180014ef6  xor     edx, edx; bInheritHandle
0x180014ef8  mov     ecx, 1000h; dwDesiredAccess
0x180014efd  call    cs:__imp_OpenProcess
0x180014f03  mov     rbx, rax
0x180014f06  test    rax, rax
0x180014f09  jz      short loc_180014F6C
0x180014f0b  mov     [rbp+TokenHandle], 0
0x180014f13  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180014f17  mov     edx, 8; DesiredAccess
0x180014f1c  mov     rcx, rax; ProcessHandle
0x180014f1f  call    cs:__imp_OpenProcessToken
0x180014f25  test    eax, eax
0x180014f27  jz      short loc_180014F62
0x180014f29  mov     [rbp+ReturnLength], 0
0x180014f30  mov     [rbp+TokenInformation], 0
0x180014f37  lea     rax, [rbp+ReturnLength]
0x180014f3b  mov     [rsp+50h+ppv], rax; ReturnLength
0x180014f40  mov     r9d, 4; TokenInformationLength
0x180014f46  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180014f4a  lea     edx, [r9+19h]; TokenInformationClass
0x180014f4e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180014f52  call    cs:__imp_GetTokenInformation
0x180014f58  mov     rcx, [rbp+TokenHandle]; hObject
0x180014f5c  call    cs:__imp_CloseHandle
0x180014f62  mov     rcx, rbx; hObject
0x180014f65  call    cs:__imp_CloseHandle
0x180014f6b  nop
0x180014f6c  mov     rcx, [rbp+var_18]
0x180014f70  test    rcx, rcx
0x180014f73  jz      short loc_180014F8A
0x180014f75  mov     [rbp+var_18], 0
0x180014f7d  mov     rdx, [rcx]
0x180014f80  mov     rax, [rdx+10h]
0x180014f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f89  nop
0x180014f8a  mov     eax, 1
0x180014f8f  mov     rbx, [rsp+50h+arg_0]
0x180014f94  add     rsp, 50h
0x180014f98  pop     rbp
0x180014f99  retn
```
