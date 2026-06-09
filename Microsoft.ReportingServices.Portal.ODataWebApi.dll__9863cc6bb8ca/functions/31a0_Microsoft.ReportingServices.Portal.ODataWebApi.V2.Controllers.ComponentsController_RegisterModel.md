# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ComponentsController::RegisterModel

- ea: `0x31a0`
- end: `0x31ac`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ComponentsController::RegisterModel`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x31a1`: `Components`

## pseudocode

```c

```

## disassembly

```asm
0x31a0  ldarg.0
0x31a1  ldstr    aComponents// "Components"
0x31a6  call     void class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component>::RegisterModel(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder, string)
0x31ab  ret
```
