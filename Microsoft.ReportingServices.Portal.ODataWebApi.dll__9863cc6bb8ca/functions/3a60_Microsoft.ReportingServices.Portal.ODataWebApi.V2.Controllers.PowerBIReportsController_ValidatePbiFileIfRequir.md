# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::ValidatePbiFileIfRequired

- ea: `0x3a60`
- end: `0x3a75`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::ValidatePbiFileIfRequired`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3910`
- `0x3a20`
- `0x3a30`

## callees

- `0x3a60`
- `0xce30`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldarg.1
0x3a61  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0x3a66  brfalse.s loc_3A74
0x3a68  ldarg.0
0x3a69  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_powerBIReportsControllerHelper
0x3a6e  ldarg.1
0x3a6f  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::ValidatePbiReportRenderingIsSupportedAndSetProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item)
0x3a74  ret
```
