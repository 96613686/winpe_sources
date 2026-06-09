# DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000c6e0`
- end: `0x18000c8d1`
- name: `?s_StopTimerCallback@PrintDeviceConfigurationService@DeviceConfiguration@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `497`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000b7f8`
- `0x18000b92c`
- `0x18000c6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7c8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c724`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c724`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c76a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c76a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000c7ba`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000c7ba`

## string_xrefs

- `0x18000c760`: `PrintDeviceConfigurationService`
- `0x18000c749`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`
- `0x18000c78f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`
- `0x18000c706`: `DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback`
- `0x18000c71b`: `ServicesActive`
- `0x18000c73a`: `Failed to open the Service Control Manager!`
- `0x18000c780`: `Failed to open the Print Device Configuration Service!`
- `0x18000c868`: `The service cannot accept stop control, it is currently %ls. hr: 0x%x`
- `0x18000c879`: `Stop control timed out, the service may be stuck. hr: 0x%x`
- `0x18000c80a`: `The system is shutting down so the service can't accept the stop control. hr: 0x%x`
- `0x18000c801`: `Failed to send the service stop control to SCM, unexpected error. hr: 0x%x`

## pseudocode

```c
void __fastcall DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  SC_HANDLE v3; // rbx
  signed int LastError; // eax
  const wchar_t *v5; // r8
  const char *v6; // r9
  SC_HANDLE v7; // [rsp+30h] [rbp-68h] BYREF
  SC_HANDLE v8; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v9[5]; // [rsp+40h] [rbp-58h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
    L"Entering stop timer callback!",
    Timer);
  v3 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v8 = v3;
  try
  {
    wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
      (int)retaddr,
      188,
      (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
      (__int64)v3,
      (__int64)"Failed to open the Service Control Manager!");
    v7 = OpenServiceW(v3, L"PrintDeviceConfigurationService", 0x30u);
    wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
      (int)retaddr,
      191,
      (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
      (__int64)v7,
      (__int64)"Failed to open the Print Device Configuration Service!");
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v7, 1u, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      switch ( LastError )
      {
        case -2147023843:
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
            L"Stop control timed out, the service may be stuck. hr: 0x%x",
            2147943453LL);
          break;
        case -2147023835:
          v9[0] = &dword_180019E84;
          v9[1] = L"stopped";
          v9[2] = L"start pending";
          v9[3] = L"stop pendingcontinue pending";
          v9[4] = L"running";
          if ( ServiceStatus.dwCurrentState >= 5 )
            v5 = L"unknown";
          else
            v5 = (const wchar_t *)v9[ServiceStatus.dwCurrentState];
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
            L"The service cannot accept stop control, it is currently %ls. hr: 0x%x",
            v5);
          break;
        case -2147023781:
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
            L"The system is shutting down so the service can't accept the stop control. hr: 0x%x",
            2147943515LL);
          break;
        default:
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
            L"Failed to send the service stop control to SCM, unexpected error. hr: 0x%x",
            (unsigned int)LastError);
          break;
      }
    }
    DeviceConfigurationTelemetry::WriteDbgTraceInfo(
      "DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback",
      L"Exiting stop timer callback!");
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v7);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE1,
      (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18000c6e0  mov     [rsp+arg_0], rbx
0x18000c6e5  push    rdi
0x18000c6e6  sub     rsp, 90h
0x18000c6ed  mov     rax, cs:__security_cookie
0x18000c6f4  xor     rax, rsp
0x18000c6f7  mov     [rsp+98h+var_10], rax
0x18000c6ff  lea     rdx, aEnteringStopTi; "Entering stop timer callback!"
0x18000c706  lea     rdi, aDeviceconfigur_24; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c70d  mov     rcx, rdi; char *
0x18000c710  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c715  mov     r8d, 1; dwDesiredAccess
0x18000c71b  lea     rdx, DatabaseName; "ServicesActive"
0x18000c722  xor     ecx, ecx; lpMachineName
0x18000c724  call    cs:__imp_OpenSCManagerW
0x18000c72a  mov     rbx, rax
0x18000c72d  mov     [rsp+98h+var_60], rax
0x18000c732  mov     rcx, [rsp+98h]
0x18000c73a  lea     rax, aFailedToOpenTh; "Failed to open the Service Control Mana"...
0x18000c741  mov     [rsp+98h+var_78], rax
0x18000c746  mov     r9, rbx
0x18000c749  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000c750  mov     edx, 0BCh
0x18000c755  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18000c75a  mov     r8d, 30h ; '0'; dwDesiredAccess
0x18000c760  lea     rdx, ServiceName; "PrintDeviceConfigurationService"
0x18000c767  mov     rcx, rbx; hSCManager
0x18000c76a  call    cs:__imp_OpenServiceW
0x18000c770  mov     rbx, rax
0x18000c773  mov     [rsp+98h+var_68], rax
0x18000c778  mov     rcx, [rsp+98h]
0x18000c780  lea     rax, aFailedToOpenTh_1; "Failed to open the Print Device Configu"...
0x18000c787  mov     [rsp+98h+var_78], rax
0x18000c78c  mov     r9, rbx
0x18000c78f  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000c796  mov     edx, 0BFh
0x18000c79b  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18000c7a0  xorps   xmm0, xmm0
0x18000c7a3  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18000c7a8  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000c7ad  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18000c7b2  mov     edx, 1; dwControl
0x18000c7b7  mov     rcx, rbx; hService
0x18000c7ba  call    cs:__imp_ControlService
0x18000c7c0  test    eax, eax
0x18000c7c2  jnz     loc_18000C888
0x18000c7c8  call    cs:__imp_GetLastError
0x18000c7ce  test    eax, eax
0x18000c7d0  jle     short loc_18000C7DA
0x18000c7d2  movzx   eax, ax
0x18000c7d5  or      eax, 80070000h
0x18000c7da  mov     r8d, 8007041Dh
0x18000c7e0  cmp     eax, r8d
0x18000c7e3  jz      loc_18000C879
0x18000c7e9  lea     r9d, [r8+8]
0x18000c7ed  cmp     eax, r9d
0x18000c7f0  jz      short loc_18000C813
0x18000c7f2  lea     r8d, [r9+36h]
0x18000c7f6  mov     rcx, rdi
0x18000c7f9  cmp     eax, r8d
0x18000c7fc  jz      short loc_18000C80A
0x18000c7fe  mov     r8d, eax
0x18000c801  lea     rdx, aFailedToSendTh; "Failed to send the service stop control"...
0x18000c808  jmp     short loc_18000C883
0x18000c80a  lea     rdx, aTheSystemIsShu; "The system is shutting down so the serv"...
0x18000c811  jmp     short loc_18000C883
0x18000c813  lea     rax, dword_180019E84
0x18000c81a  mov     [rsp+98h+var_58], rax
0x18000c81f  lea     rax, aStopped; "stopped"
0x18000c826  mov     [rsp+98h+var_50], rax
0x18000c82b  lea     rax, aStartPending; "start pending"
0x18000c832  mov     [rsp+98h+var_48], rax
0x18000c837  lea     rax, aStopPendingcon; "stop pendingcontinue pending"
0x18000c83e  mov     [rsp+98h+var_40], rax
0x18000c843  lea     rax, aRunning; "running"
0x18000c84a  mov     [rsp+98h+var_38], rax
0x18000c84f  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 5
0x18000c854  jnb     short loc_18000C861
0x18000c856  mov     eax, [rsp+98h+ServiceStatus.dwCurrentState]
0x18000c85a  mov     r8, [rsp+rax*8+98h+var_58]
0x18000c85f  jmp     short loc_18000C868
0x18000c861  lea     r8, aUnknown; "unknown"
0x18000c868  lea     rdx, aTheServiceCann; "The service cannot accept stop control,"...
0x18000c86f  mov     rcx, rdi; char *
0x18000c872  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000c877  jmp     short loc_18000C888
0x18000c879  lea     rdx, aStopControlTim; "Stop control timed out, the service may"...
0x18000c880  mov     rcx, rdi; char *
0x18000c883  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000c888  lea     rdx, aExitingStopTim; "Exiting stop timer callback!"
0x18000c88f  mov     rcx, rdi; char *
0x18000c892  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c897  nop
0x18000c898  lea     rcx, [rsp+98h+var_68]
0x18000c89d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c8a2  nop
0x18000c8a3  lea     rcx, [rsp+98h+var_60]
0x18000c8a8  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c8ad  nop
0x18000c8ae  jmp     short $+2
0x18000c8b0  mov     rcx, [rsp+98h+var_10]
0x18000c8b8  xor     rcx, rsp; StackCookie
0x18000c8bb  call    __security_check_cookie
0x18000c8c0  mov     rbx, [rsp+98h+arg_0]
0x18000c8c8  add     rsp, 90h
0x18000c8cf  pop     rdi
0x18000c8d0  retn
```
