# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SearchItems

- ea: `0x7fa0`
- end: `0x7fdf`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SearchItems`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x660`
- `0x7fa0`

## pseudocode

```c

```

## disassembly

```asm
0x7fa0  ldarg.1
0x7fa1  ldloca.s 0
0x7fa3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7fa8  brtrue.s loc_7FB1
0x7faa  ldarg.0
0x7fab  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x7fb0  ret
0x7fb1  ldarg.2
0x7fb2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7fb7  brfalse.s loc_7FC5
0x7fb9  ldarg.0
0x7fba  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_Error_SearchTextNullOrEmpty()
0x7fbf  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x7fc4  ret
0x7fc5  ldarg.0
0x7fc6  ldarg.0
0x7fc7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7fcc  ldarg.0
0x7fcd  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7fd2  ldloc.0
0x7fd3  ldarg.2
0x7fd4  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SearchItems(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, string)
0x7fd9  callvirt T0x2B00006D
0x7fde  ret
```
