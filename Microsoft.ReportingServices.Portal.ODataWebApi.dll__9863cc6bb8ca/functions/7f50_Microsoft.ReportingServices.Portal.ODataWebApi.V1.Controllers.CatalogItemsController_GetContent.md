# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetContent

- ea: `0x7f50`
- end: `0x7f7d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetContent`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x7e70`
- `0x7f50`

## pseudocode

```c

```

## disassembly

```asm
0x7f50  ldarg.1
0x7f51  ldloca.s 0
0x7f53  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7f58  brtrue.s loc_7F61
0x7f5a  ldarg.0
0x7f5b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x7f60  ret
0x7f61  ldarg.0
0x7f62  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7f67  ldarg.0
0x7f68  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7f6d  ldloc.0
0x7f6e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContent(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x7f73  stloc.1
0x7f74  ldarg.0
0x7f75  ldloc.1
0x7f76  ldarg.2
0x7f77  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GenerateContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath oDataPath)
0x7f7c  ret
```
