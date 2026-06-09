# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::DeleteItems

- ea: `0x7fe0`
- end: `0x8040`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::DeleteItems`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f50`

## callees

- `0x6a0`
- `0x7fe0`

## string_xrefs

- `0x7fee`: `CatalogItemPaths`
- `0x8008`: `CatalogItemPaths`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  ldarg.0
0x7fe1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x7fe6  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x7feb  brfalse.s loc_7FFA
0x7fed  ldarg.1
0x7fee  ldstr    aCatalogitempat// "CatalogItemPaths"
0x7ff3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x7ff8  brtrue.s loc_8007
0x7ffa  ldarg.0
0x7ffb  ldarg.0
0x7ffc  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetModelStateValidationErrors()
0x8001  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8006  ret
0x8007  ldarg.1
0x8008  ldstr    aCatalogitempat// "CatalogItemPaths"
0x800d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x8012  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<string>
0x8017  stloc.0
0x8018  ldloc.0
0x8019  brtrue.s loc_8027
0x801b  ldarg.0
0x801c  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied()
0x8021  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8026  ret
0x8027  ldarg.0
0x8028  ldarg.0
0x8029  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x802e  ldarg.0
0x802f  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8034  ldloc.0
0x8035  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.BulkOperationsResult [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::DeleteItems(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x803a  callvirt T0x2B0000B9
0x803f  ret
```
