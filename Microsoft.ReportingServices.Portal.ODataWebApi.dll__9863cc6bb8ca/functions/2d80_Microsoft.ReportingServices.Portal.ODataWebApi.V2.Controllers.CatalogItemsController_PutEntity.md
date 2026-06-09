# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::PutEntity

- ea: `0x2d80`
- end: `0x2dda`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::PutEntity`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2cd0`
- `0x2d80`
- `0x76f0`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  ldarg.0
0x2d81  ldarg.2
0x2d82  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiFile(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem entity)
0x2d87  ldarg.0
0x2d88  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogItemControllerHelper()
0x2d8d  ldarg.1
0x2d8e  ldloca.s 0
0x2d90  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::IsRequestByPath(string, string&)
0x2d95  stloc.1
0x2d96  ldloca.s 2
0x2d98  initobj  [mscorlib]System.Guid
0x2d9e  ldloc.1
0x2d9f  brtrue.s loc_2DAB
0x2da1  ldarg.1
0x2da2  ldloca.s 2
0x2da4  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2da9  brfalse.s loc_2DD8
0x2dab  ldloc.1
0x2dac  brtrue.s loc_2DC3
0x2dae  ldarg.0
0x2daf  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2db4  ldarg.0
0x2db5  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2dba  ldloc.2
0x2dbb  ldarg.2
0x2dbc  ldnull
0x2dbd  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x2dc2  ret
0x2dc3  ldarg.0
0x2dc4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2dc9  ldarg.0
0x2dca  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2dcf  ldloc.0
0x2dd0  ldarg.2
0x2dd1  ldnull
0x2dd2  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x2dd7  ret
0x2dd8  ldc.i4.0
0x2dd9  ret
```
