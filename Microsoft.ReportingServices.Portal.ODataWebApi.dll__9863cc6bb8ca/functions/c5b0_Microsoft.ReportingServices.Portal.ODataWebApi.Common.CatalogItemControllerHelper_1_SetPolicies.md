# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::SetPolicies

- ea: `0xc5b0`
- end: `0xc656`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::SetPolicies`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc5b0`

## pseudocode

```c

```

## disassembly

```asm
0xc5b0  ldarg.2
0xc5b1  brtrue.s loc_C5BF
0xc5b3  ldarg.0
0xc5b4  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc5b9  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0xc5be  ret
0xc5bf  ldarg.0
0xc5c0  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc5c5  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xc5ca  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xc5cf  brfalse.s loc_C5DE
0xc5d1  ldarg.2
0xc5d2  ldstr    aPolicy// "Policy"
0xc5d7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xc5dc  brtrue.s loc_C5F5
0xc5de  ldarg.0
0xc5df  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc5e4  ldarg.0
0xc5e5  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc5ea  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xc5ef  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xc5f4  ret
0xc5f5  ldarg.2
0xc5f6  ldstr    aPolicy// "Policy"
0xc5fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xc600  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemPolicy
0xc605  stloc.0
0xc606  ldarg.0
0xc607  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc60c  ldarg.0
0xc60d  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc612  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc617  ldarg.1
0xc618  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xc61d  stloc.1
0xc61e  ldloc.1
0xc61f  brtrue.s loc_C62D
0xc621  ldarg.0
0xc622  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc627  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xc62c  ret
0xc62d  ldarg.0
0xc62e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc633  ldarg.0
0xc634  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc639  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc63e  ldloc.1
0xc63f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0xc644  ldloc.0
0xc645  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetItemPolicy(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemPolicy)
0xc64a  ldarg.0
0xc64b  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc650  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::Ok()
0xc655  ret
```
