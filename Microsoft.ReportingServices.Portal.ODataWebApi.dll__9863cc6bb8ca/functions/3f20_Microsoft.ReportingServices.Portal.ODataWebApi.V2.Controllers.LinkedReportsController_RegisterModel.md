# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.LinkedReportsController::RegisterModel

- ea: `0x3f20`
- end: `0x3f62`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.LinkedReportsController::RegisterModel`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x3f21`: `LinkedReports`
- `0x3f31`: `UpdateCacheSnapshot`
- `0x3f56`: `ParentPath`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldarg.0
0x3f21  ldstr    aLinkedreports// "LinkedReports"
0x3f26  call     void class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::RegisterModel(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder, string)
0x3f2b  ldarg.0
0x3f2c  callvirt T0x2B00006A
0x3f31  ldstr    aUpdatecachesna// "UpdateCacheSnapshot"
0x3f36  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Action(string)
0x3f3b  callvirt T0x2B00006B
0x3f40  pop
0x3f41  ldarg.0
0x3f42  callvirt T0x2B00006A
0x3f47  ldstr    aReparent// "Reparent"
0x3f4c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Action(string)
0x3f51  callvirt T0x2B000055
0x3f56  ldstr    aParentpath// "ParentPath"
0x3f5b  callvirt T0x2B000031
0x3f60  pop
0x3f61  ret
```
