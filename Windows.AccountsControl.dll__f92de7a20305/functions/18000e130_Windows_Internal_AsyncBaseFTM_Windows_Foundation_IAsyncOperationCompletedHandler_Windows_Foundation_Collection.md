# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18000e130`
- end: `0x18000e23a`
- name: `?CheckExecutionEnvironment@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `266`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e130`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e1bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e18d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e18d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e205`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e16a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e16a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e19d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e19d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e1f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e1f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckExecutionEnvironment(
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
0x18000e130  mov     [rsp-8+arg_0], rbx
0x18000e135  push    rbp
0x18000e136  mov     rbp, rsp
0x18000e139  sub     rsp, 50h
0x18000e13d  mov     [rbp+var_18], 0
0x18000e145  mov     [rbp+var_8], 0
0x18000e14d  lea     rax, [rbp+var_18]
0x18000e151  mov     [rsp+50h+ppv], rax; ppv
0x18000e156  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000e15d  xor     edx, edx; pUnkOuter
0x18000e15f  lea     r8d, [rdx+1]; dwClsContext
0x18000e163  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000e16a  call    cs:__imp_CoCreateInstance
0x18000e170  test    eax, eax
0x18000e172  js      short loc_18000E18D
0x18000e174  mov     rcx, [rbp+var_18]
0x18000e178  mov     rax, [rcx]
0x18000e17b  lea     r8, [rbp+var_8]
0x18000e17f  mov     edx, 4
0x18000e184  mov     rax, [rax+20h]
0x18000e188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e18d  call    cs:__imp_GetCurrentProcessId
0x18000e193  mov     r8d, eax; dwProcessId
0x18000e196  xor     edx, edx; bInheritHandle
0x18000e198  mov     ecx, 1000h; dwDesiredAccess
0x18000e19d  call    cs:__imp_OpenProcess
0x18000e1a3  mov     rbx, rax
0x18000e1a6  test    rax, rax
0x18000e1a9  jz      short loc_18000E20C
0x18000e1ab  mov     [rbp+TokenHandle], 0
0x18000e1b3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000e1b7  mov     edx, 8; DesiredAccess
0x18000e1bc  mov     rcx, rax; ProcessHandle
0x18000e1bf  call    cs:__imp_OpenProcessToken
0x18000e1c5  test    eax, eax
0x18000e1c7  jz      short loc_18000E202
0x18000e1c9  mov     [rbp+ReturnLength], 0
0x18000e1d0  mov     [rbp+TokenInformation], 0
0x18000e1d7  lea     rax, [rbp+ReturnLength]
0x18000e1db  mov     [rsp+50h+ppv], rax; ReturnLength
0x18000e1e0  mov     r9d, 4; TokenInformationLength
0x18000e1e6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000e1ea  lea     edx, [r9+19h]; TokenInformationClass
0x18000e1ee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000e1f2  call    cs:__imp_GetTokenInformation
0x18000e1f8  mov     rcx, [rbp+TokenHandle]; hObject
0x18000e1fc  call    cs:__imp_CloseHandle
0x18000e202  mov     rcx, rbx; hObject
0x18000e205  call    cs:__imp_CloseHandle
0x18000e20b  nop
0x18000e20c  mov     rcx, [rbp+var_18]
0x18000e210  test    rcx, rcx
0x18000e213  jz      short loc_18000E22A
0x18000e215  mov     [rbp+var_18], 0
0x18000e21d  mov     rdx, [rcx]
0x18000e220  mov     rax, [rdx+10h]
0x18000e224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e229  nop
0x18000e22a  mov     eax, 1
0x18000e22f  mov     rbx, [rsp+50h+arg_0]
0x18000e234  add     rsp, 50h
0x18000e238  pop     rbp
0x18000e239  retn
```
