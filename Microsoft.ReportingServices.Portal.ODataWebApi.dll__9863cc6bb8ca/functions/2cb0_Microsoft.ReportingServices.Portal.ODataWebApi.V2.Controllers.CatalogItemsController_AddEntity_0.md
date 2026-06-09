# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::AddEntity_0

- ea: `0x2cb0`
- end: `0x2ccf`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::AddEntity_0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x2cb0`
- `0x2cd0`
- `0x2d00`
- `0x7d60`

## pseudocode

```c

```

## disassembly

```asm
0x2cb0  ldarg.0
0x2cb1  ldarg.1
0x2cb2  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiFile(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem entity)
0x2cb7  ldarg.1
0x2cb8  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_IsComment()
0x2cbd  brfalse.s loc_2CC6
0x2cbf  ldarg.0
0x2cc0  ldarg.1
0x2cc1  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidateImageFile(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem entity)
0x2cc6  ldarg.0
0x2cc7  ldarg.1
0x2cc8  ldarg.2
0x2cc9  call     instance bool Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::AddEntity(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem entity, [out] class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem& createdEntity)
0x2cce  ret
```
