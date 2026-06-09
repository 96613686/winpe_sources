# ServiceMain(ulong,ushort * *)

- ea: `0x18000de50`
- end: `0x18000de70`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `32`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f760`
- `0x180010328`

## string_xrefs

- `0x18000de54`: `ServiceMain entered`
- `0x18000de5b`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  PrintScanBrokerTelemetry::WriteDbgTraceInfo("ServiceMain", L"ServiceMain entered");
  wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::main();
}

```

## disassembly

```asm
0x18000de50  sub     rsp, 28h
0x18000de54  lea     rdx, aServicemainEnt; "ServiceMain entered"
0x18000de5b  lea     rcx, aServicemain_0; "ServiceMain"
0x18000de62  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000de67  add     rsp, 28h
0x18000de6b  jmp     ?main@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@QEAAXXZ; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::main(void)
```
