# wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(ulong,ulong)

- ea: `0x1800148b4`
- end: `0x180014948`
- name: `?update_status@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@AEAAXKK@Z`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800057d0`
- `0x1800141ec`
- `0x180014330`

## callees

- `0x180003ca0`
- `0x180014660`
- `0x1800148b4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014922`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014922`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(
        __int64 a1,
        DWORD a2,
        DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  BOOL result; // eax
  const struct winrt::impl::slim_source_location *v5; // rdx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+28h] [rbp-38h]
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ServiceStatus.dwServiceType = 96;
  ServiceStatus.dwCurrentState = a2;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a2 == 4 || a2 == 1 )
  {
    ServiceStatus.dwControlsAccepted = 1025;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  }
  v3 = *(SERVICE_STATUS_HANDLE *)(a1 + 32);
  v6 = 0;
  v7 = 0;
  result = SetServiceStatus(v3, &ServiceStatus);
  if ( !result )
    winrt::throw_last_error((winrt *)&v6, v5);
  return result;
}

```

## disassembly

```asm
0x1800148b4  push    rbp
0x1800148b6  mov     rbp, rsp
0x1800148b9  sub     rsp, 60h
0x1800148bd  mov     rax, cs:__security_cookie
0x1800148c4  xor     rax, rsp
0x1800148c7  mov     [rbp+var_8], rax
0x1800148cb  xor     eax, eax
0x1800148cd  mov     [rbp+ServiceStatus.dwServiceType], 60h ; '`'
0x1800148d4  mov     [rbp+ServiceStatus.dwCurrentState], edx
0x1800148d7  xorps   xmm0, xmm0
0x1800148da  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x1800148dd  movups  xmmword ptr [rbp+ServiceStatus.dwControlsAccepted], xmm0
0x1800148e1  mov     [rbp+ServiceStatus.dwWin32ExitCode], r8d
0x1800148e5  cmp     edx, 4
0x1800148e8  jz      short loc_180014907
0x1800148ea  cmp     edx, 1
0x1800148ed  jz      short loc_180014907
0x1800148ef  mov     eax, 1
0x1800148f4  lock xadd [rcx+28h], eax
0x1800148f9  inc     eax
0x1800148fb  mov     [rbp+ServiceStatus.dwWaitHint], 1388h
0x180014902  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180014905  jmp     short loc_18001490E
0x180014907  mov     [rbp+ServiceStatus.dwControlsAccepted], 401h
0x18001490e  mov     rcx, [rcx+20h]; hServiceStatus
0x180014912  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180014916  mov     [rbp+var_40], 0
0x18001491d  movdqu  [rbp+var_38], xmm0
0x180014922  call    cs:__imp_SetServiceStatus
0x180014928  test    eax, eax
0x18001492a  jz      short loc_18001493E
0x18001492c  mov     rcx, [rbp+var_8]
0x180014930  xor     rcx, rsp; StackCookie
0x180014933  call    __security_check_cookie
0x180014938  add     rsp, 60h
0x18001493c  pop     rbp
0x18001493d  retn
0x18001493e  lea     rcx, [rbp+var_40]; this
0x180014942  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
