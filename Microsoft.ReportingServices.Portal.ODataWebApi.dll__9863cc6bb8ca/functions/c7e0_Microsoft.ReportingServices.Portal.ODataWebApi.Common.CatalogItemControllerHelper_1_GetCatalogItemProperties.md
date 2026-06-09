# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetCatalogItemProperties

- ea: `0xc7e0`
- end: `0xc86c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetCatalogItemProperties`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc7e0`

## pseudocode

```c

```

## disassembly

```asm
0xc7e0  ldarg.2
0xc7e1  brtrue.s loc_C7EF
0xc7e3  ldarg.0
0xc7e4  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc7e9  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0xc7ee  ret
0xc7ef  ldarg.0
0xc7f0  ldarg.1
0xc7f1  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::GetItem(string)
0xc7f6  stloc.0
0xc7f7  ldarg.2
0xc7f8  ldstr    asc_1043E// "'"
0xc7fd  ldsfld   string [mscorlib]System.String::Empty
0xc802  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc807  ldc.i4.1
0xc808  newarr   [mscorlib]System.Char
0xc80d  dup
0xc80e  ldc.i4.0
0xc80f  ldc.i4.s 0x2C
0xc811  stelem.i2
0xc812  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc817  ldsfld   class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> class <>c<var<u1>>::<>9__20_0
0xc81c  dup
0xc81d  brtrue.s loc_C836
0xc81f  pop
0xc820  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xc825  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property class <>c<var<u1>>::<GetCatalogItemProperties>b__20_0(string)
0xc82b  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor(object, native int)
0xc830  dup
0xc831  stsfld   class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> class <>c<var<u1>>::<>9__20_0
0xc836  call     T0x2B0000F2
0xc83b  call     T0x2B00008C
0xc840  stloc.1
0xc841  ldarg.0
0xc842  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc847  ldarg.0
0xc848  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc84d  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc852  ldloc.0
0xc853  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0xc858  ldloc.1
0xc859  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetItemProperties(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xc85e  stloc.2
0xc85f  ldarg.0
0xc860  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc865  ldloc.2
0xc866  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xc86b  ret
```
