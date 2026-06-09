# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GetDependentItems

- ea: `0x2360`
- end: `0x2407`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GetDependentItems`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2360`

## pseudocode

```c

```

## disassembly

```asm
0x2360  ldarg.0
0x2361  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_CatalogItemControllerHelper()
0x2366  ldarg.1
0x2367  ldloca.s 0
0x2369  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::IsRequestByPath(string, string&)
0x236e  stloc.1
0x236f  ldloca.s 2
0x2371  initobj  [mscorlib]System.Guid
0x2377  ldloc.1
0x2378  brtrue.s loc_238B
0x237a  ldarg.1
0x237b  ldloca.s 2
0x237d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2382  brtrue.s loc_238B
0x2384  ldarg.0
0x2385  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0x238a  ret
0x238b  ldarg.2
0x238c  brfalse.s loc_23D5
0x238e  ldloc.1
0x238f  brtrue.s loc_23A5
0x2391  ldarg.0
0x2392  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x2397  ldarg.0
0x2398  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x239d  ldloc.2
0x239e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x23a3  br.s     loc_23B7
0x23a5  ldarg.0
0x23a6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x23ab  ldarg.0
0x23ac  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x23b1  ldloc.0
0x23b2  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x23b7  stloc.s  4
0x23b9  ldloc.s  4
0x23bb  brtrue.s loc_23C4
0x23bd  ldarg.0
0x23be  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0x23c3  ret
0x23c4  ldloc.s  4
0x23c6  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x23cb  ldarg.2
0x23cc  beq.s    loc_23D5
0x23ce  ldarg.0
0x23cf  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0x23d4  ret
0x23d5  ldloc.1
0x23d6  brtrue.s loc_23EC
0x23d8  ldarg.0
0x23d9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x23de  ldarg.0
0x23df  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x23e4  ldloc.2
0x23e5  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDependentItems(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x23ea  br.s     loc_23FE
0x23ec  ldarg.0
0x23ed  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x23f2  ldarg.0
0x23f3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x23f8  ldloc.0
0x23f9  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDependentItems(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x23fe  stloc.3
0x23ff  ldarg.0
0x2400  ldloc.3
0x2401  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0x2406  ret
```
