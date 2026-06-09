# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetContentTrusted

- ea: `0xc2f0`
- end: `0xc3d5`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetContentTrusted`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc2f0`

## pseudocode

```c

```

## disassembly

```asm
0xc2f0  ldarg.2
0xc2f1  brtrue.s loc_C2FF
0xc2f3  ldarg.0
0xc2f4  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc2f9  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0xc2fe  ret
0xc2ff  ldarg.0
0xc300  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc305  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xc30a  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xc30f  brfalse.s loc_C31E
0xc311  ldarg.2
0xc312  ldsfld   string class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::TrustedProcessTokenString
0xc317  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xc31c  brtrue.s loc_C335
0xc31e  ldarg.0
0xc31f  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc324  ldarg.0
0xc325  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc32a  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xc32f  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xc334  ret
0xc335  nop
0xc336  ldarg.2
0xc337  ldsfld   string class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::TrustedProcessTokenString
0xc33c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xc341  castclass [mscorlib]System.String
0xc346  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValididateTokenOrException(string)
0xc34b  leave.s  loc_C381
0xc34d  stloc.3
0xc34e  ldarg.0
0xc34f  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc354  ldloc.3
0xc355  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc35a  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xc35f  stloc.s  4
0xc361  leave.s  loc_C3D2
0xc363  pop
0xc364  ldc.i4   0x198
0xc369  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xc36e  stloc.s  5
0xc370  ldarg.0
0xc371  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc376  ldloc.s  5
0xc378  callvirt instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0xc37d  stloc.s  4
0xc37f  leave.s  loc_C3D2
0xc381  ldarg.1
0xc382  ldloca.s 0
0xc384  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xc389  brtrue.s loc_C397
0xc38b  ldarg.0
0xc38c  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc391  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xc396  ret
0xc397  ldarg.0
0xc398  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc39d  ldarg.0
0xc39e  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc3a3  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc3a8  ldloc.0
0xc3a9  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContentTrusted(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xc3ae  unbox.any var<u1>
0xc3b3  stloc.1
0xc3b4  ldc.i4.1
0xc3b5  newarr   [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment
0xc3ba  dup
0xc3bb  ldc.i4.0
0xc3bc  ldnull
0xc3bd  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ValueSegment::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType)
0xc3c2  stelem.ref
0xc3c3  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::.ctor(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment[])
0xc3c8  stloc.2
0xc3c9  ldarg.0
0xc3ca  ldloc.1
0xc3cb  ldloc.2
0xc3cc  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::GenerateContent(var<u1>, !!T0)
0xc3d1  ret
0xc3d2  ldloc.s  4
0xc3d4  ret
```
