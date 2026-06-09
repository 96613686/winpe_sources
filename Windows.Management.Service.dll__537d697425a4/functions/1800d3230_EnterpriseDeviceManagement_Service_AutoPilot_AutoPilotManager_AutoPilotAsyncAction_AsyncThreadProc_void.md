# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::AsyncThreadProc(void *)

- ea: `0x1800d3230`
- end: `0x1800d3370`
- name: `?AsyncThreadProc@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAKPEAX@Z`
- size: `320`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180067398`
- `0x180067e34`
- `0x180067e54`
- `0x180077d0c`
- `0x1800d3230`
- `0x1800d7ac4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d32ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d32ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800d3356`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800d3356`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d32e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d32e4`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800d3363`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800d3363`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800d3242`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800d3242`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800d333e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800d333e`

## string_xrefs

- `0x1800d325c`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d32cf`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d3318`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::AsyncThreadProc(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager **Parameter)
{
  int v2; // eax
  unsigned int v3; // edi
  const char *v5; // r9
  unsigned int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF
  EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager **v10; // [rsp+40h] [rbp+18h] BYREF

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v10 = Parameter;
    if ( Parameter )
      (*((void (__fastcall **)(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager **))*Parameter + 1))(Parameter);
    EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(Parameter[2], 1);
    phModule = 0;
    if ( !GetModuleHandleExW(
            4u,
            (LPCWSTR)&Microsoft::Windows::Autopilot::RipAndReusePolicyManager::DownloadProfileFromNetwork,
            &phModule) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        v5);
    SetEvent(Parameter[4]);
    v6 = ((__int64 (__fastcall *)(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *))Parameter[1])(Parameter[2]);
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147023436 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        (const char *)v6,
        v7);
    EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(Parameter[2], 0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    RoUninitialize();
    if ( phModule )
      FreeLibraryAndExitThread(phModule, 0);
    ExitThread(0);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x135,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
    (const char *)(unsigned int)v2,
    v7);
  return v3;
}

```

## disassembly

```asm
0x1800d3230  mov     [rsp+arg_0], rbx
0x1800d3235  push    rdi; int
0x1800d3236  sub     rsp, 20h
0x1800d323a  mov     rbx, rcx
0x1800d323d  mov     ecx, 1
0x1800d3242  call    cs:__imp_RoInitialize
0x1800d3249  nop     dword ptr [rax+rax+00h]
0x1800d324e  mov     edi, eax
0x1800d3250  test    eax, eax
0x1800d3252  jns     short loc_1800D327B
0x1800d3254  mov     rcx, [rsp+28h]; this
0x1800d3259  mov     r9d, eax; char *
0x1800d325c  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d3263  mov     edx, 135h; void *
0x1800d3268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d326d  mov     eax, edi
0x1800d326f  mov     rbx, [rsp+28h+arg_0]
0x1800d3274  add     rsp, 20h
0x1800d3278  pop     rdi
0x1800d3279  retn
0x1800d327b  mov     [rsp+28h+arg_10], rbx
0x1800d3280  test    rbx, rbx
0x1800d3283  jz      short loc_1800D3295
0x1800d3285  mov     rax, [rbx]
0x1800d3288  mov     rcx, rbx
0x1800d328b  mov     rax, [rax+8]
0x1800d328f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3294  nop
0x1800d3295  mov     dl, 1; bool
0x1800d3297  mov     rcx, [rbx+10h]; this
0x1800d329b  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d32a0  mov     [rsp+28h+phModule], 0
0x1800d32a9  lea     r8, [rsp+28h+phModule]; phModule
0x1800d32ae  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x1800d32b5  mov     ecx, 4; dwFlags
0x1800d32ba  call    cs:__imp_GetModuleHandleExW
0x1800d32c1  nop     dword ptr [rax+rax+00h]
0x1800d32c6  test    eax, eax
0x1800d32c8  jnz     short loc_1800D32E0
0x1800d32ca  mov     rcx, [rsp+28h]; this
0x1800d32cf  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d32d6  mov     edx, 166h; void *
0x1800d32db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d32e0  mov     rcx, [rbx+20h]; hEvent
0x1800d32e4  call    cs:__imp_SetEvent
0x1800d32eb  nop     dword ptr [rax+rax+00h]
0x1800d32f0  mov     rcx, [rbx+10h]
0x1800d32f4  mov     rax, [rbx+8]
0x1800d32f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32fd  mov     edx, 80000000h
0x1800d3302  lea     ecx, [rax+rdx]
0x1800d3305  test    edx, ecx
0x1800d3307  jnz     short loc_1800D3329
0x1800d3309  cmp     eax, 800705B4h
0x1800d330e  jz      short loc_1800D3329
0x1800d3310  mov     rcx, [rsp+28h]; this
0x1800d3315  mov     r9d, eax; char *
0x1800d3318  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d331f  mov     edx, 148h; void *
0x1800d3324  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d3329  xor     edx, edx; bool
0x1800d332b  mov     rcx, [rbx+10h]; this
0x1800d332f  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d3334  lea     rcx, [rsp+28h+arg_10]
0x1800d3339  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d333e  call    cs:__imp_RoUninitialize
0x1800d3345  nop     dword ptr [rax+rax+00h]
0x1800d334a  mov     rcx, [rsp+28h+phModule]; hLibModule
0x1800d334f  test    rcx, rcx
0x1800d3352  jz      short loc_1800D3363
0x1800d3354  xor     edx, edx; dwExitCode
0x1800d3356  call    cs:__imp_FreeLibraryAndExitThread
0x1800d335d  nop     dword ptr [rax+rax+00h]
0x1800d3362  int     3; Trap to Debugger
0x1800d3363  call    cs:__imp_ExitThread
```
