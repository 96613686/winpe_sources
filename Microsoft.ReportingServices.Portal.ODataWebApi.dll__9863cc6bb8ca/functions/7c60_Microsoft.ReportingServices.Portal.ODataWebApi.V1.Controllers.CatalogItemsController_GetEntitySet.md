# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetEntitySet

- ea: `0x7c60`
- end: `0x7c94`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetEntitySet`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b90`

## callees

- `0x7c60`

## pseudocode

```c

```

## disassembly

```asm
0x7c60  ldarg.1
0x7c61  brtrue.s loc_7C75
0x7c63  ldarg.0
0x7c64  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7c69  ldarg.0
0x7c6a  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7c6f  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItems(class [mscorlib]System.Security.Principal.IPrincipal)
0x7c74  ret
0x7c75  ldarg.1
0x7c76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x7c7b  ldnull
0x7c7c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7c81  pop
0x7c82  ldarg.0
0x7c83  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7c88  ldarg.0
0x7c89  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7c8e  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItems(class [mscorlib]System.Security.Principal.IPrincipal)
0x7c93  ret
```
