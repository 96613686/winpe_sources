# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::AutoPilotAsyncAction::AsyncThreadProc(void *)

- ea: `0x1800d0d60`
- end: `0x1800d0e7b`
- name: `?AsyncThreadProc@AutoPilotAsyncAction@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAKPEAX@Z`
- size: `283`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180067008`
- `0x180067a34`
- `0x180067a54`
- `0x18007748c`
- `0x1800d0d60`
- `0x1800d54a4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d0de3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d0de3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800d0e6d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800d0e6d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d0e07`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d0e07`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800d0e74`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800d0e74`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800d0d72`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800d0d72`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800d0e5b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800d0e5b`

## string_xrefs

- `0x1800d0d86`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d0df2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d0e35`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
0x1800d0d60  mov     [rsp+arg_0], rbx
0x1800d0d65  push    rdi; int
0x1800d0d66  sub     rsp, 20h
0x1800d0d6a  mov     rbx, rcx
0x1800d0d6d  mov     ecx, 1
0x1800d0d72  call    cs:__imp_RoInitialize
0x1800d0d78  mov     edi, eax
0x1800d0d7a  test    eax, eax
0x1800d0d7c  jns     short loc_1800D0DA4
0x1800d0d7e  mov     rcx, [rsp+28h]; this
0x1800d0d83  mov     r9d, eax; char *
0x1800d0d86  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d0d8d  mov     edx, 135h; void *
0x1800d0d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0d97  mov     eax, edi
0x1800d0d99  mov     rbx, [rsp+28h+arg_0]
0x1800d0d9e  add     rsp, 20h
0x1800d0da2  pop     rdi
0x1800d0da3  retn
0x1800d0da4  mov     [rsp+28h+arg_10], rbx
0x1800d0da9  test    rbx, rbx
0x1800d0dac  jz      short loc_1800D0DBE
0x1800d0dae  mov     rax, [rbx]
0x1800d0db1  mov     rcx, rbx
0x1800d0db4  mov     rax, [rax+8]
0x1800d0db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0dbd  nop
0x1800d0dbe  mov     dl, 1; bool
0x1800d0dc0  mov     rcx, [rbx+10h]; this
0x1800d0dc4  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d0dc9  mov     [rsp+28h+phModule], 0
0x1800d0dd2  lea     r8, [rsp+28h+phModule]; phModule
0x1800d0dd7  lea     rdx, ?DownloadProfileFromNetwork@RipAndReusePolicyManager@Autopilot@Windows@Microsoft@@UEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z; lpModuleName
0x1800d0dde  mov     ecx, 4; dwFlags
0x1800d0de3  call    cs:__imp_GetModuleHandleExW
0x1800d0de9  test    eax, eax
0x1800d0deb  jnz     short loc_1800D0E03
0x1800d0ded  mov     rcx, [rsp+28h]; this
0x1800d0df2  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d0df9  mov     edx, 166h; void *
0x1800d0dfe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d0e03  mov     rcx, [rbx+20h]; hEvent
0x1800d0e07  call    cs:__imp_SetEvent
0x1800d0e0d  mov     rcx, [rbx+10h]
0x1800d0e11  mov     rax, [rbx+8]
0x1800d0e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0e1a  mov     edx, 80000000h
0x1800d0e1f  lea     ecx, [rax+rdx]
0x1800d0e22  test    edx, ecx
0x1800d0e24  jnz     short loc_1800D0E46
0x1800d0e26  cmp     eax, 800705B4h
0x1800d0e2b  jz      short loc_1800D0E46
0x1800d0e2d  mov     rcx, [rsp+28h]; this
0x1800d0e32  mov     r9d, eax; char *
0x1800d0e35  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d0e3c  mov     edx, 148h; void *
0x1800d0e41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d0e46  xor     edx, edx; bool
0x1800d0e48  mov     rcx, [rbx+10h]; this
0x1800d0e4c  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d0e51  lea     rcx, [rsp+28h+arg_10]
0x1800d0e56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0e5b  call    cs:__imp_RoUninitialize
0x1800d0e61  mov     rcx, [rsp+28h+phModule]; dwExitCode
0x1800d0e66  test    rcx, rcx
0x1800d0e69  jz      short loc_1800D0E74
0x1800d0e6b  xor     edx, edx; dwExitCode
0x1800d0e6d  call    cs:__imp_FreeLibraryAndExitThread
0x1800d0e73  int     3; Trap to Debugger
0x1800d0e74  call    cs:__imp_ExitThread
```
