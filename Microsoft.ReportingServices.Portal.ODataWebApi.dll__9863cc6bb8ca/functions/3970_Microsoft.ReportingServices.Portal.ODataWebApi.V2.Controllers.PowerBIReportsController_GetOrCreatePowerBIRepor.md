# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::GetOrCreatePowerBIReport

- ea: `0x3970`
- end: `0x3a14`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::GetOrCreatePowerBIReport`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xdc20`

## callees

- `0x3970`

## string_xrefs

- `0x39f6`: `Attempting to re-upload a PowerBIReport to an invalid ID (GUID={0}) Either wrong GUID, or the object isn't a PowerBiReport`

## pseudocode

```c

```

## disassembly

```asm
0x3970  ldarg.0
0x3971  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogItemControllerHelper()
0x3976  ldarg.1
0x3977  ldloca.s 0
0x3979  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::IsRequestByPath(string, string&)
0x397e  brfalse.s loc_39D0
0x3980  ldarg.0
0x3981  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0x3986  ldarg.0
0x3987  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x398c  ldloc.0
0x398d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x3992  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0x3997  dup
0x3998  brtrue.s loc_39A1
0x399a  ldloc.0
0x399b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException::.ctor(string)
0x39a0  throw
0x39a1  stloc.1
0x39a2  leave.s  loc_3A12
0x39a4  pop
0x39a5  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::.ctor()
0x39aa  dup
0x39ab  ldloc.0
0x39ac  call     string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetNameFromFullPath(string)
0x39b1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x39b6  dup
0x39b7  ldloc.0
0x39b8  call     string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetParentPathFromFullPath(string)
0x39bd  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x39c2  dup
0x39c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x39c8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0x39cd  stloc.1
0x39ce  leave.s  loc_3A12
0x39d0  ldarg.0
0x39d1  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0x39d6  ldarg.0
0x39d7  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x39dc  ldarg.1
0x39dd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x39e2  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x39e7  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0x39ec  dup
0x39ed  brtrue.s loc_3A11
0x39ef  ldarg.0
0x39f0  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0x39f5  ldc.i4.2
0x39f6  ldstr    aAttemptingToRe_0// "Attempting to re-upload a PowerBIReport"...
0x39fb  ldarg.1
0x39fc  call     string [mscorlib]System.String::Format(string, object)
0x3a01  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3a06  ldc.i4   0x194
0x3a0b  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x3a10  throw
0x3a11  ret
0x3a12  ldloc.1
0x3a13  ret
```
