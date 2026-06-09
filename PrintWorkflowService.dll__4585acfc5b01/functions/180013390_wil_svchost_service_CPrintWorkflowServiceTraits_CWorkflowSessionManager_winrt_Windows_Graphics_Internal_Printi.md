# wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::main(void)

- ea: `0x180013390`
- end: `0x180013408`
- name: `?main@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@QEAAXXZ`
- size: `120`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010c10`

## callees

- `0x180013390`
- `0x1800141ec`
- `0x180014660`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800133c4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800133c4`

## pseudocode

```c
__int64 __fastcall wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::main(
        __int64 a1,
        const struct winrt::impl::slim_source_location *a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const struct winrt::impl::slim_source_location *v3; // rdx
  void *v4; // rcx
  __int64 result; // rax
  const winrt::hresult_error *v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+28h] [rbp-20h] BYREF
  __int128 v8; // [rsp+30h] [rbp-18h]

  v7 = 0;
  v8 = 0;
  if ( !(_QWORD)g_serviceWithPsa )
    winrt::throw_last_error((winrt *)&v7, a2);
  v2 = RegisterServiceCtrlHandlerExW(
         L"PrintWorkflowUserSvc",
         _lambda_0f0035fc44f51ac94b24a57affc0d9cb_::_lambda_invoker_cdecl_,
         &g_serviceWithPsa);
  qword_180084270 = (__int64)v2;
  v7 = 0;
  v8 = 0;
  if ( !v2 )
    winrt::throw_last_error((winrt *)&v7, v3);
  try
  {
    result = wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::start(v4);
  }
  catch ( const winrt::hresult_error *v6 )
  {
    return wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::stop(
             &g_serviceWithPsa,
             *((unsigned int *)v6 + 3));
  }
  return result;
}

```

## disassembly

```asm
0x180013390  sub     rsp, 48h
0x180013394  mov     [rsp+48h+var_20], 0
0x18001339c  xorps   xmm0, xmm0
0x18001339f  movdqu  [rsp+48h+var_18], xmm0
0x1800133a5  cmp     qword ptr cs:?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A, 0; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> g_serviceWithPsa
0x1800133ad  jz      short loc_1800133F2
0x1800133af  lea     r8, ?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A; lpContext
0x1800133b6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0f0035fc44f51ac94b24a57affc0d9cb_@@CA@KKPEAX0@Z; lpHandlerProc
0x1800133bd  lea     rcx, ServiceName; "PrintWorkflowUserSvc"
0x1800133c4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800133ca  mov     cs:qword_180084270, rax
0x1800133d1  mov     [rsp+48h+var_20], 0
0x1800133d9  xorps   xmm0, xmm0
0x1800133dc  movdqu  [rsp+48h+var_18], xmm0
0x1800133e2  test    rax, rax
0x1800133e5  jz      short loc_1800133FD
0x1800133e7  call    ?start@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@AEAAXXZ; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::start(void)
0x1800133ec  nop
0x1800133ed  add     rsp, 48h
0x1800133f1  retn
0x1800133f2  lea     rcx, [rsp+48h+var_20]; this
0x1800133f7  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x1800133fd  lea     rcx, [rsp+48h+var_20]; this
0x180013402  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
