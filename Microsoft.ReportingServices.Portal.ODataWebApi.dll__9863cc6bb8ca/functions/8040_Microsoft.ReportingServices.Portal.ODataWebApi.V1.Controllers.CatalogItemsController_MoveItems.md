# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::MoveItems

- ea: `0x8040`
- end: `0x80ce`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::MoveItems`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f60`

## callees

- `0x6a0`
- `0x8040`

## string_xrefs

- `0x804e`: `CatalogItemPaths`
- `0x8075`: `CatalogItemPaths`
- `0x805b`: `TargetPath`
- `0x8095`: `TargetPath`

## pseudocode

```c

```

## disassembly

```asm
0x8040  ldarg.0
0x8041  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x8046  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x804b  brfalse.s loc_8067
0x804d  ldarg.1
0x804e  ldstr    aCatalogitempat// "CatalogItemPaths"
0x8053  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8058  brfalse.s loc_8067
0x805a  ldarg.1
0x805b  ldstr    aTargetpath// "TargetPath"
0x8060  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8065  brtrue.s loc_8074
0x8067  ldarg.0
0x8068  ldarg.0
0x8069  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetModelStateValidationErrors()
0x806e  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8073  ret
0x8074  ldarg.1
0x8075  ldstr    aCatalogitempat// "CatalogItemPaths"
0x807a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x807f  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<string>
0x8084  stloc.0
0x8085  ldloc.0
0x8086  brtrue.s loc_8094
0x8088  ldarg.0
0x8089  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied()
0x808e  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8093  ret
0x8094  ldarg.1
0x8095  ldstr    aTargetpath// "TargetPath"
0x809a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x809f  isinst   [mscorlib]System.String
0x80a4  stloc.1
0x80a5  ldloc.1
0x80a6  brtrue.s loc_80B4
0x80a8  ldarg.0
0x80a9  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied()
0x80ae  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x80b3  ret
0x80b4  ldarg.0
0x80b5  ldarg.0
0x80b6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x80bb  ldarg.0
0x80bc  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x80c1  ldloc.0
0x80c2  ldloc.1
0x80c3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.BulkOperationsResult [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::MoveItems(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, string)
0x80c8  callvirt T0x2B0000B9
0x80cd  ret
```
