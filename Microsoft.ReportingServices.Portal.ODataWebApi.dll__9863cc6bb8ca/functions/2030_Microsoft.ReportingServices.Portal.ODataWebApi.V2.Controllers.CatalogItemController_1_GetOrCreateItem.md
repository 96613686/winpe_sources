# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GetOrCreateItem

- ea: `0x2030`
- end: `0x20fa`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GetOrCreateItem`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2030`

## string_xrefs

- `0x20dc`: `Attempting to re-upload a CatalogItem to an invalid ID (GUID={0}) Bad GUID`

## pseudocode

```c

```

## disassembly

```asm
0x2030  ldarg.0
0x2031  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_CatalogItemControllerHelper()
0x2036  ldarg.1
0x2037  ldloca.s 0
0x2039  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::IsRequestByPath(string, string&)
0x203e  brfalse.s loc_20AC
0x2040  ldarg.0
0x2041  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_CatalogRepository()
0x2046  ldarg.0
0x2047  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x204c  ldloc.0
0x204d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x2052  isinst   var<u1>
0x2057  unbox.any var<u1>
0x205c  dup
0x205d  box      var<u1>
0x2062  brtrue.s loc_206B
0x2064  ldloc.0
0x2065  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException::.ctor(string)
0x206a  throw
0x206b  stloc.1
0x206c  leave    loc_20F8
0x2071  pop
0x2072  call     T0x2B000043
0x2077  dup
0x2078  box      var<u1>
0x207d  ldloc.0
0x207e  call     string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetNameFromFullPath(string)
0x2083  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x2088  dup
0x2089  box      var<u1>
0x208e  ldloc.0
0x208f  call     string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetParentPathFromFullPath(string)
0x2094  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x2099  dup
0x209a  box      var<u1>
0x209f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20a4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0x20a9  stloc.1
0x20aa  leave.s  loc_20F8
0x20ac  ldarg.0
0x20ad  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_CatalogRepository()
0x20b2  ldarg.0
0x20b3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x20b8  ldarg.1
0x20b9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x20be  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x20c3  isinst   var<u1>
0x20c8  unbox.any var<u1>
0x20cd  dup
0x20ce  box      var<u1>
0x20d3  brtrue.s loc_20F7
0x20d5  ldarg.0
0x20d6  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0x20db  ldc.i4.2
0x20dc  ldstr    aAttemptingToRe// "Attempting to re-upload a CatalogItem t"...
0x20e1  ldarg.1
0x20e2  call     string [mscorlib]System.String::Format(string, object)
0x20e7  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x20ec  ldc.i4   0x194
0x20f1  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x20f6  throw
0x20f7  ret
0x20f8  ldloc.1
0x20f9  ret
```
