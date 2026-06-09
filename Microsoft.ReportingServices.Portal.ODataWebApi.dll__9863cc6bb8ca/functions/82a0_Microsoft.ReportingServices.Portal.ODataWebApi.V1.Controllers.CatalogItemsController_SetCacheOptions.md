# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SetCacheOptions

- ea: `0x82a0`
- end: `0x8314`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SetCacheOptions`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x82a0`

## string_xrefs

- `0x82b1`: `cacheOptions`
- `0x82cb`: `cacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x82a0  ldarg.0
0x82a1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x82a6  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x82ab  brfalse.s loc_82BD
0x82ad  ldarg.3
0x82ae  brfalse.s loc_82BD
0x82b0  ldarg.3
0x82b1  ldstr    aCacheoptions// "cacheOptions"
0x82b6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x82bb  brtrue.s loc_82CA
0x82bd  ldarg.0
0x82be  ldarg.0
0x82bf  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetModelStateValidationErrors()
0x82c4  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x82c9  ret
0x82ca  ldarg.3
0x82cb  ldstr    aCacheoptions// "cacheOptions"
0x82d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x82d5  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions
0x82da  stloc.0
0x82db  ldarg.0
0x82dc  ldarga.s 1
0x82de  constrained. [mscorlib]System.Guid
0x82e4  callvirt instance string [mscorlib]System.Object::ToString()
0x82e9  ldnull
0x82ea  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetEntity(!!T0, string)
0x82ef  stloc.1
0x82f0  ldarg.0
0x82f1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x82f6  ldarg.0
0x82f7  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x82fc  ldloc.1
0x82fd  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x8302  ldloc.0
0x8303  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetItemCacheOptions(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions)
0x8308  ldarg.0
0x8309  ldc.i4   0xCC
0x830e  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x8313  ret
```
