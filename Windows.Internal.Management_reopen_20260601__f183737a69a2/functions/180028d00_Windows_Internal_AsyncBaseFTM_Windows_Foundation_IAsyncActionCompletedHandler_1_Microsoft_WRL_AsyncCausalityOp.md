# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionStartAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180028d00`
- end: `0x180028e20`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?AsyncActionStartAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `288`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009be4`
- `0x180028d00`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028d63`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028da1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028df9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028d3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028d3a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028dda`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028dda`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028d79`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180028d79`

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
0x180028d00  mov     [rsp-8+arg_0], rbx
0x180028d05  push    rbp
0x180028d06  mov     rbp, rsp
0x180028d09  sub     rsp, 50h
0x180028d0d  mov     [rbp+var_10], 0
0x180028d15  mov     [rbp+var_8], 0
0x180028d1d  lea     rax, [rbp+var_10]
0x180028d21  mov     [rsp+50h+ppv], rax; ppv
0x180028d26  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180028d2d  xor     edx, edx; pUnkOuter
0x180028d2f  lea     r8d, [rdx+1]; dwClsContext
0x180028d33  lea     rcx, CLSID_GlobalOptions; rclsid
0x180028d3a  call    cs:__imp_CoCreateInstance
0x180028d41  nop     dword ptr [rax+rax+00h]
0x180028d46  test    eax, eax
0x180028d48  js      short loc_180028D63
0x180028d4a  mov     rcx, [rbp+var_10]
0x180028d4e  mov     rax, [rcx]
0x180028d51  lea     r8, [rbp+var_8]
0x180028d55  mov     edx, 4
0x180028d5a  mov     rax, [rax+20h]
0x180028d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d63  call    cs:__imp_GetCurrentProcessId
0x180028d6a  nop     dword ptr [rax+rax+00h]
0x180028d6f  mov     r8d, eax; dwProcessId
0x180028d72  xor     edx, edx; bInheritHandle
0x180028d74  mov     ecx, 1000h; dwDesiredAccess
0x180028d79  call    cs:__imp_OpenProcess
0x180028d80  nop     dword ptr [rax+rax+00h]
0x180028d85  mov     rbx, rax
0x180028d88  test    rax, rax
0x180028d8b  jz      short loc_180028E06
0x180028d8d  mov     [rbp+TokenHandle], 0
0x180028d95  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180028d99  mov     edx, 8; DesiredAccess
0x180028d9e  mov     rcx, rax; ProcessHandle
0x180028da1  call    cs:__imp_OpenProcessToken
0x180028da8  nop     dword ptr [rax+rax+00h]
0x180028dad  test    eax, eax
0x180028daf  jz      short loc_180028DF6
0x180028db1  mov     [rbp+ReturnLength], 0
0x180028db8  mov     [rbp+TokenInformation], 0
0x180028dbf  lea     rax, [rbp+ReturnLength]
0x180028dc3  mov     [rsp+50h+ppv], rax; ReturnLength
0x180028dc8  mov     r9d, 4; TokenInformationLength
0x180028dce  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180028dd2  lea     edx, [r9+19h]; TokenInformationClass
0x180028dd6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180028dda  call    cs:__imp_GetTokenInformation
0x180028de1  nop     dword ptr [rax+rax+00h]
0x180028de6  mov     rcx, [rbp+TokenHandle]; hObject
0x180028dea  call    cs:__imp_CloseHandle
0x180028df1  nop     dword ptr [rax+rax+00h]
0x180028df6  mov     rcx, rbx; hObject
0x180028df9  call    cs:__imp_CloseHandle
0x180028e00  nop     dword ptr [rax+rax+00h]
0x180028e05  nop
0x180028e06  lea     rcx, [rbp+var_10]
0x180028e0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028e0f  mov     eax, 1
0x180028e14  mov     rbx, [rsp+50h+arg_0]
0x180028e19  add     rsp, 50h
0x180028e1d  pop     rbp
0x180028e1e  retn
```
