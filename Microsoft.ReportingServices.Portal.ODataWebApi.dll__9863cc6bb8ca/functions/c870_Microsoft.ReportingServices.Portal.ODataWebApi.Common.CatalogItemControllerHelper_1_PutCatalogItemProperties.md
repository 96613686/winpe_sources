# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::PutCatalogItemProperties

- ea: `0xc870`
- end: `0xc8fe`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::PutCatalogItemProperties`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc870`

## pseudocode

```c

```

## disassembly

```asm
0xc870  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor()
0xc875  stloc.0
0xc876  ldarg.0
0xc877  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc87c  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xc881  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0xc886  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xc88b  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<string>::get_Result()
0xc890  stloc.1
0xc891  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor()
0xc896  stloc.0
0xc897  ldloc.1
0xc898  ldloc.0
0xc899  call     void [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::PopulateObject(string, object)
0xc89e  leave.s  loc_C8CA
0xc8a0  stloc.3
0xc8a1  ldstr    aInvalidPayload// "Invalid payload: {0}"
0xc8a6  ldloc.3
0xc8a7  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc8ac  call     string [mscorlib]System.String::Format(string, object)
0xc8b1  call     T0x2B0000F3
0xc8b6  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0xc8bb  ldarg.0
0xc8bc  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc8c1  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest()
0xc8c6  stloc.s  4
0xc8c8  leave.s  loc_C8FB
0xc8ca  ldarg.0
0xc8cb  ldarg.1
0xc8cc  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::GetItem(string)
0xc8d1  stloc.2
0xc8d2  ldarg.0
0xc8d3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc8d8  ldarg.0
0xc8d9  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc8de  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc8e3  ldloc.2
0xc8e4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0xc8e9  ldloc.0
0xc8ea  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetItemProperties(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xc8ef  ldarg.0
0xc8f0  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc8f5  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::Ok()
0xc8fa  ret
0xc8fb  ldloc.s  4
0xc8fd  ret
```
