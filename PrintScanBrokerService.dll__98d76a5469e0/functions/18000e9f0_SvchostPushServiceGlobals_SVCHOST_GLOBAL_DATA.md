# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x18000e9f0`
- end: `0x18000ea19`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `41`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f760`
- `0x180010f6c`

## string_xrefs

- `0x18000e9f9`: `SvchostPushServiceGlobals called`
- `0x18000ea00`: `SvchostPushServiceGlobals`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  __int64 v2; // rcx

  PrintScanBrokerTelemetry::WriteDbgTraceInfo("SvchostPushServiceGlobals", L"SvchostPushServiceGlobals called");
  wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::set_globals(
    v2,
    a1);
}

```

## disassembly

```asm
0x18000e9f0  push    rbx
0x18000e9f2  sub     rsp, 20h
0x18000e9f6  mov     rbx, rcx
0x18000e9f9  lea     rdx, aSvchostpushser_0; "SvchostPushServiceGlobals called"
0x18000ea00  lea     rcx, aSvchostpushser_1; "SvchostPushServiceGlobals"
0x18000ea07  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ea0c  mov     rdx, rbx
0x18000ea0f  add     rsp, 20h
0x18000ea13  pop     rbx
0x18000ea14  jmp     ?set_globals@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@QEAAXPEAU_SVCHOST_GLOBAL_DATA@@@Z; wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::set_globals(_SVCHOST_GLOBAL_DATA *)
```
