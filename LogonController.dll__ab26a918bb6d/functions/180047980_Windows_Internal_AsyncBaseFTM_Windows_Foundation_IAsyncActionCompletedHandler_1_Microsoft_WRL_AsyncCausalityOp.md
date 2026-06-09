# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180047980`
- end: `0x180047a74`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?c_WebDialogAsyncAction@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `244`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000df10`
- `0x180047980`
- `0x18009d010`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x1800479ed`
- `KERNEL32!OpenProcess` at `0x1800479ed`
- `KERNEL32!GetCurrentProcessId` at `0x1800479dd`
- `KERNEL32!GetCurrentProcessId` at `0x1800479dd`
- `KERNEL32!CloseHandle` at `0x180047a4c`
- `KERNEL32!CloseHandle` at `0x180047a55`
- `KERNEL32!CloseHandle` at `0x180047a4c`
- `KERNEL32!CloseHandle` at `0x180047a55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800479ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800479ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047a0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047a0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047a42`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const c_WebDialogAsyncAction,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&ppv);
  return 1;
}

```

## disassembly

```asm
0x180047980  mov     [rsp-8+arg_0], rbx
0x180047985  push    rbp
0x180047986  mov     rbp, rsp
0x180047989  sub     rsp, 50h
0x18004798d  xor     edx, edx; pUnkOuter
0x18004798f  mov     [rbp+var_10], 0
0x180047997  lea     rax, [rbp+var_10]
0x18004799b  mov     [rbp+var_8], 0
0x1800479a3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800479aa  mov     [rsp+50h+ppv], rax; ppv
0x1800479af  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800479b6  lea     r8d, [rdx+1]; dwClsContext
0x1800479ba  call    cs:__imp_CoCreateInstance
0x1800479c0  test    eax, eax
0x1800479c2  js      short loc_1800479DD
0x1800479c4  mov     rcx, [rbp+var_10]
0x1800479c8  lea     r8, [rbp+var_8]
0x1800479cc  mov     edx, 4
0x1800479d1  mov     rax, [rcx]
0x1800479d4  mov     rax, [rax+20h]
0x1800479d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479dd  call    cs:__imp_GetCurrentProcessId
0x1800479e3  xor     edx, edx; bInheritHandle
0x1800479e5  mov     ecx, 1000h; dwDesiredAccess
0x1800479ea  mov     r8d, eax; dwProcessId
0x1800479ed  call    cs:__imp_OpenProcess
0x1800479f3  mov     rbx, rax
0x1800479f6  test    rax, rax
0x1800479f9  jz      short loc_180047A5B
0x1800479fb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800479ff  mov     [rbp+TokenHandle], 0
0x180047a07  mov     edx, 8; DesiredAccess
0x180047a0c  mov     rcx, rax; ProcessHandle
0x180047a0f  call    cs:__imp_OpenProcessToken
0x180047a15  test    eax, eax
0x180047a17  jz      short loc_180047A52
0x180047a19  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180047a1d  lea     rax, [rbp+ReturnLength]
0x180047a21  mov     r9d, 4; TokenInformationLength
0x180047a27  mov     [rbp+ReturnLength], 0
0x180047a2e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180047a32  mov     [rbp+TokenInformation], 0
0x180047a39  mov     [rsp+50h+ppv], rax; ReturnLength
0x180047a3e  lea     edx, [r9+19h]; TokenInformationClass
0x180047a42  call    cs:__imp_GetTokenInformation
0x180047a48  mov     rcx, [rbp+TokenHandle]; hObject
0x180047a4c  call    cs:__imp_CloseHandle
0x180047a52  mov     rcx, rbx; hObject
0x180047a55  call    cs:__imp_CloseHandle
0x180047a5b  lea     rcx, [rbp+var_10]
0x180047a5f  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180047a64  mov     rbx, [rsp+50h+arg_0]
0x180047a69  mov     eax, 1
0x180047a6e  add     rsp, 50h
0x180047a72  pop     rbp
0x180047a73  retn
```
