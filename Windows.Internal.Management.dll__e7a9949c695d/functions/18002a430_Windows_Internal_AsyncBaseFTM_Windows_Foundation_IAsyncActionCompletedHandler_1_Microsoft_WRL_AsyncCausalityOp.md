# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionStartAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002a430`
- end: `0x18002a525`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?AsyncActionStartAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `245`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000992c`
- `0x18002a430`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a4bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a48d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a48d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a505`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a46a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a46a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a4f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a4f2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a49d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a49d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const AsyncActionStartAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rbx
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  ppv = 0;
  v10 = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 4, &v10);
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
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x18002a430  mov     [rsp-8+arg_0], rbx
0x18002a435  push    rbp
0x18002a436  mov     rbp, rsp
0x18002a439  sub     rsp, 50h
0x18002a43d  mov     [rbp+var_10], 0
0x18002a445  mov     [rbp+var_8], 0
0x18002a44d  lea     rax, [rbp+var_10]
0x18002a451  mov     [rsp+50h+ppv], rax; ppv
0x18002a456  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18002a45d  xor     edx, edx; pUnkOuter
0x18002a45f  lea     r8d, [rdx+1]; dwClsContext
0x18002a463  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002a46a  call    cs:__imp_CoCreateInstance
0x18002a470  test    eax, eax
0x18002a472  js      short loc_18002A48D
0x18002a474  mov     rcx, [rbp+var_10]
0x18002a478  mov     rax, [rcx]
0x18002a47b  lea     r8, [rbp+var_8]
0x18002a47f  mov     edx, 4
0x18002a484  mov     rax, [rax+20h]
0x18002a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a48d  call    cs:__imp_GetCurrentProcessId
0x18002a493  mov     r8d, eax; dwProcessId
0x18002a496  xor     edx, edx; bInheritHandle
0x18002a498  mov     ecx, 1000h; dwDesiredAccess
0x18002a49d  call    cs:__imp_OpenProcess
0x18002a4a3  mov     rbx, rax
0x18002a4a6  test    rax, rax
0x18002a4a9  jz      short loc_18002A50C
0x18002a4ab  mov     [rbp+TokenHandle], 0
0x18002a4b3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002a4b7  mov     edx, 8; DesiredAccess
0x18002a4bc  mov     rcx, rax; ProcessHandle
0x18002a4bf  call    cs:__imp_OpenProcessToken
0x18002a4c5  test    eax, eax
0x18002a4c7  jz      short loc_18002A502
0x18002a4c9  mov     [rbp+ReturnLength], 0
0x18002a4d0  mov     [rbp+TokenInformation], 0
0x18002a4d7  lea     rax, [rbp+ReturnLength]
0x18002a4db  mov     [rsp+50h+ppv], rax; ReturnLength
0x18002a4e0  mov     r9d, 4; TokenInformationLength
0x18002a4e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002a4ea  lea     edx, [r9+19h]; TokenInformationClass
0x18002a4ee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002a4f2  call    cs:__imp_GetTokenInformation
0x18002a4f8  mov     rcx, [rbp+TokenHandle]; hObject
0x18002a4fc  call    cs:__imp_CloseHandle
0x18002a502  mov     rcx, rbx; hObject
0x18002a505  call    cs:__imp_CloseHandle
0x18002a50b  nop
0x18002a50c  lea     rcx, [rbp+var_10]
0x18002a510  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a515  mov     eax, 1
0x18002a51a  mov     rbx, [rsp+50h+arg_0]
0x18002a51f  add     rsp, 50h
0x18002a523  pop     rbp
0x18002a524  retn
```
