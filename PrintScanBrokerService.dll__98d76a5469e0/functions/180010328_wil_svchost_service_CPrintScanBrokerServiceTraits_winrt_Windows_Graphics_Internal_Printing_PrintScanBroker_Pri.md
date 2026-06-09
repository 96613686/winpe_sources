# wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::main(void)

- ea: `0x180010328`
- end: `0x1800103a0`
- name: `?main@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@QEAAXXZ`
- size: `120`
- prototype: `__int64 __fastcall(__int64, const struct winrt::impl::slim_source_location *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000de50`

## callees

- `0x180010328`
- `0x180010f90`
- `0x180011428`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001035c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001035c`

## string_xrefs

- `0x180010355`: `PrintScanBrokerService`

## pseudocode

```c
__int64 __fastcall wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::main(
        __int64 a1,
        const struct winrt::impl::slim_source_location *a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const struct winrt::impl::slim_source_location *v3; // rdx
  __int64 result; // rax
  const winrt::hresult_error *v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]

  v6 = 0;
  v7 = 0;
  if ( !(_QWORD)g_serviceWithBroker )
    winrt::throw_last_error((winrt *)&v6, a2);
  v2 = RegisterServiceCtrlHandlerExW(
         L"PrintScanBrokerService",
         _lambda_599221ef3c8bd9bf5d5f17bf482e7ead_::_lambda_invoker_cdecl_,
         &g_serviceWithBroker);
  qword_180060F48 = (__int64)v2;
  v6 = 0;
  v7 = 0;
  if ( !v2 )
    winrt::throw_last_error((winrt *)&v6, v3);
  try
  {
    result = wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::start();
  }
  catch ( const winrt::hresult_error *v5 )
  {
    return wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::stop(
             &g_serviceWithBroker,
             *((unsigned int *)v5 + 3));
  }
  result = wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::start();
}

```

## disassembly

```asm
0x180010328  sub     rsp, 48h
0x18001032c  mov     [rsp+48h+var_20], 0
0x180010334  xorps   xmm0, xmm0
0x180010337  movdqu  [rsp+48h+var_18], xmm0
0x18001033d  cmp     qword ptr cs:?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A, 0; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler> g_serviceWithBroker
0x180010345  jz      short loc_18001038A
0x180010347  lea     r8, ?g_serviceWithBroker@@3V?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@A; lpContext
0x18001034e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_599221ef3c8bd9bf5d5f17bf482e7ead_@@CA@KKPEAX0@Z; lpHandlerProc
0x180010355  lea     rcx, ServiceName; "PrintScanBrokerService"
0x18001035c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180010362  mov     cs:qword_180060F48, rax
0x180010369  mov     [rsp+48h+var_20], 0
0x180010371  xorps   xmm0, xmm0
0x180010374  movdqu  [rsp+48h+var_18], xmm0
0x18001037a  test    rax, rax
0x18001037d  jz      short loc_180010395
0x18001037f  call    ?start@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@AEAAXXZ; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::start(void)
0x180010384  nop
0x180010385  add     rsp, 48h
0x180010389  retn
0x18001038a  lea     rcx, [rsp+48h+var_20]; this
0x18001038f  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x180010395  lea     rcx, [rsp+48h+var_20]; this
0x18001039a  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
