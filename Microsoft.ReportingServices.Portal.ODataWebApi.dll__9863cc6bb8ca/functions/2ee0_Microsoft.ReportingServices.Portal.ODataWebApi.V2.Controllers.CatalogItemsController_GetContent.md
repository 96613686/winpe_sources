# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::GetContent

- ea: `0x2ee0`
- end: `0x2f3e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::GetContent`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2ee0`
- `0x76f0`
- `0x7e70`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldarg.0
0x2ee1  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogItemControllerHelper()
0x2ee6  ldarg.1
0x2ee7  ldloca.s 0
0x2ee9  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::IsRequestByPath(string, string&)
0x2eee  stloc.1
0x2eef  ldloca.s 2
0x2ef1  initobj  [mscorlib]System.Guid
0x2ef7  ldloc.1
0x2ef8  brtrue.s loc_2F0B
0x2efa  ldarg.1
0x2efb  ldloca.s 2
0x2efd  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2f02  brtrue.s loc_2F0B
0x2f04  ldarg.0
0x2f05  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x2f0a  ret
0x2f0b  ldloc.1
0x2f0c  brtrue.s loc_2F22
0x2f0e  ldarg.0
0x2f0f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2f14  ldarg.0
0x2f15  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2f1a  ldloc.2
0x2f1b  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContent(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x2f20  br.s     loc_2F34
0x2f22  ldarg.0
0x2f23  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2f28  ldarg.0
0x2f29  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2f2e  ldloc.0
0x2f2f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContent(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x2f34  stloc.3
0x2f35  ldarg.0
0x2f36  ldloc.3
0x2f37  ldarg.2
0x2f38  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GenerateContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath oDataPath)
0x2f3d  ret
```
