# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180084630`
- end: `0x18008473a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180084630`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800846bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800846bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008468d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008468d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800846fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800846fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084705`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800846f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800846f2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008469d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008469d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008466a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008466a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x180084630  mov     [rsp-8+arg_0], rbx
0x180084635  push    rbp
0x180084636  mov     rbp, rsp
0x180084639  sub     rsp, 50h
0x18008463d  mov     [rbp+var_18], 0
0x180084645  mov     [rbp+var_8], 0
0x18008464d  lea     rax, [rbp+var_18]
0x180084651  mov     [rsp+50h+ppv], rax; ppv
0x180084656  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18008465d  xor     edx, edx; pUnkOuter
0x18008465f  lea     r8d, [rdx+1]; dwClsContext
0x180084663  lea     rcx, CLSID_GlobalOptions; rclsid
0x18008466a  call    cs:__imp_CoCreateInstance
0x180084670  test    eax, eax
0x180084672  js      short loc_18008468D
0x180084674  mov     rcx, [rbp+var_18]
0x180084678  mov     rax, [rcx]
0x18008467b  lea     r8, [rbp+var_8]
0x18008467f  mov     edx, 4
0x180084684  mov     rax, [rax+20h]
0x180084688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008468d  call    cs:__imp_GetCurrentProcessId
0x180084693  mov     r8d, eax; dwProcessId
0x180084696  xor     edx, edx; bInheritHandle
0x180084698  mov     ecx, 1000h; dwDesiredAccess
0x18008469d  call    cs:__imp_OpenProcess
0x1800846a3  mov     rbx, rax
0x1800846a6  test    rax, rax
0x1800846a9  jz      short loc_18008470C
0x1800846ab  mov     [rbp+TokenHandle], 0
0x1800846b3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800846b7  mov     edx, 8; DesiredAccess
0x1800846bc  mov     rcx, rax; ProcessHandle
0x1800846bf  call    cs:__imp_OpenProcessToken
0x1800846c5  test    eax, eax
0x1800846c7  jz      short loc_180084702
0x1800846c9  mov     [rbp+ReturnLength], 0
0x1800846d0  mov     [rbp+TokenInformation], 0
0x1800846d7  lea     rax, [rbp+ReturnLength]
0x1800846db  mov     [rsp+50h+ppv], rax; ReturnLength
0x1800846e0  mov     r9d, 4; TokenInformationLength
0x1800846e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800846ea  lea     edx, [r9+19h]; TokenInformationClass
0x1800846ee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800846f2  call    cs:__imp_GetTokenInformation
0x1800846f8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800846fc  call    cs:__imp_CloseHandle
0x180084702  mov     rcx, rbx; hObject
0x180084705  call    cs:__imp_CloseHandle
0x18008470b  nop
0x18008470c  mov     rcx, [rbp+var_18]
0x180084710  test    rcx, rcx
0x180084713  jz      short loc_18008472A
0x180084715  mov     [rbp+var_18], 0
0x18008471d  mov     rdx, [rcx]
0x180084720  mov     rax, [rdx+10h]
0x180084724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084729  nop
0x18008472a  mov     eax, 1
0x18008472f  mov     rbx, [rsp+50h+arg_0]
0x180084734  add     rsp, 50h
0x180084738  pop     rbp
0x180084739  retn
```
