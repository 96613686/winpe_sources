# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiFile

- ea: `0x2cd0`
- end: `0x2cfc`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiFile`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2cb0`
- `0x2d80`
- `0x2de0`

## callees

- `0x2cd0`
- `0x2fc0`

## pseudocode

```c

```

## disassembly

```asm
0x2cd0  ldarg.1
0x2cd1  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x2cd6  ldc.i4.s 0xB
0x2cd8  bne.un.s loc_2CFB
0x2cda  ldarg.0
0x2cdb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_systemService
0x2ce0  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0x2ce5  brfalse.s loc_2CFB
0x2ce7  ldarg.1
0x2ce8  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0x2ced  brfalse.s loc_2CFB
0x2cef  ldarg.0
0x2cf0  ldarg.1
0x2cf1  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0x2cf6  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiReportRenderingIsSupportedAndSetProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item)
0x2cfb  ret
```
