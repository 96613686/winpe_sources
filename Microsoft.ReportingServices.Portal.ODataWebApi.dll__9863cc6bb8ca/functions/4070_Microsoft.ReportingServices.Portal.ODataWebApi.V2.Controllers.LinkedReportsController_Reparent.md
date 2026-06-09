# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.LinkedReportsController::Reparent

- ea: `0x4070`
- end: `0x410e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.LinkedReportsController::Reparent`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x4070`

## string_xrefs

- `0x407e`: `ParentPath`
- `0x4092`: `ParentPath`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldarg.0
0x4071  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x4076  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x407b  brfalse.s loc_408A
0x407d  ldarg.2
0x407e  ldstr    aParentpath// "ParentPath"
0x4083  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x4088  brtrue.s loc_4091
0x408a  ldarg.0
0x408b  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::BadRequest()
0x4090  ret
0x4091  ldarg.2
0x4092  ldstr    aParentpath// "ParentPath"
0x4097  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x409c  castclass [mscorlib]System.String
0x40a1  stloc.0
0x40a2  ldarg.0
0x40a3  ldarg.1
0x40a4  ldnull
0x40a5  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::GetEntity(!!T0, string)
0x40aa  stloc.2
0x40ab  ldarg.0
0x40ac  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::get_CatalogRepository()
0x40b1  ldarg.0
0x40b2  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x40b7  ldloc.0
0x40b8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x40bd  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x40c2  stloc.1
0x40c3  leave.s  loc_40EC
0x40c5  stloc.3
0x40c6  ldarg.0
0x40c7  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::get_Logger()
0x40cc  ldc.i4.4
0x40cd  ldstr    aInvalidPayload_0// "Invalid payload: new parent is not an i"...
0x40d2  ldloc.3
0x40d3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x40d8  call     string [mscorlib]System.String::Format(string, object)
0x40dd  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x40e2  ldarg.0
0x40e3  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::BadRequest()
0x40e8  stloc.s  4
0x40ea  leave.s  loc_410B
0x40ec  ldarg.0
0x40ed  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::get_CatalogRepository()
0x40f2  ldarg.0
0x40f3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x40f8  ldloc.2
0x40f9  ldloc.1
0x40fa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x40ff  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetLinkedReportLink(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport, string)
0x4104  ldarg.0
0x4105  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport>::Ok()
0x410a  ret
0x410b  ldloc.s  4
0x410d  ret
```
