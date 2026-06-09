# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetAllowedActions

- ea: `0xc430`
- end: `0xc4f7`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetAllowedActions`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc430`

## pseudocode

```c

```

## disassembly

```asm
0xc430  ldarg.0
0xc431  ldarg.1
0xc432  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::GetCatalogItemByKey(string)
0xc437  stloc.0
0xc438  ldloc.0
0xc439  brtrue.s loc_C44C
0xc43b  ldarg.0
0xc43c  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc441  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0xc446  stloc.2
0xc447  leave    loc_C4F5
0xc44c  ldarg.0
0xc44d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc452  ldarg.0
0xc453  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc458  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc45d  ldloc.0
0xc45e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0xc463  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetAllowedActions(class [mscorlib]System.Security.Principal.IPrincipal, string)
0xc468  ldsfld   class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction> class <>c<var<u1>>::<>9__16_0
0xc46d  dup
0xc46e  brtrue.s loc_C487
0xc470  pop
0xc471  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xc476  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction class <>c<var<u1>>::<GetAllowedActions>b__16_0(string)
0xc47c  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction>::.ctor(object, native int)
0xc481  dup
0xc482  stsfld   class [mscorlib]System.Func`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction> class <>c<var<u1>>::<>9__16_0
0xc487  call     T0x2B000088
0xc48c  call     T0x2B000089
0xc491  stloc.1
0xc492  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xc497  ldc.i4.s 0xE
0xc499  stloc.3
0xc49a  ldloca.s 3
0xc49c  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches
0xc4a2  callvirt instance string [mscorlib]System.Object::ToString()
0xc4a7  ldc.i4.0
0xc4a8  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, bool)
0xc4ad  brtrue.s loc_C4DA
0xc4af  ldloc.1
0xc4b0  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction, bool> class <>c<var<u1>>::<>9__16_1
0xc4b5  dup
0xc4b6  brtrue.s loc_C4CF
0xc4b8  pop
0xc4b9  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xc4be  ldftn    instance bool class <>c<var<u1>>::<GetAllowedActions>b__16_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction)
0xc4c4  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction, bool>::.ctor(object, native int)
0xc4c9  dup
0xc4ca  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction, bool> class <>c<var<u1>>::<>9__16_1
0xc4cf  call     T0x2B0000F1
0xc4d4  call     T0x2B000089
0xc4d9  stloc.1
0xc4da  ldarg.0
0xc4db  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc4e0  ldloc.1
0xc4e1  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xc4e6  stloc.2
0xc4e7  leave.s  loc_C4F5
0xc4e9  pop
0xc4ea  ldc.i4   0x193
0xc4ef  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xc4f4  throw
0xc4f5  ldloc.2
0xc4f6  ret
```
