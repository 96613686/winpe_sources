# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::PatchEntity

- ea: `0x7db0`
- end: `0x7e65`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::PatchEntity`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7db0`

## string_xrefs

- `0x7df5`: `Invalid PATCH request, Path does not end with Name of catalog item.`
- `0x7dff`: `Path does not end with Name of catalog item.`

## pseudocode

```c

```

## disassembly

```asm
0x7db0  ldarg.1
0x7db1  ldloca.s 0
0x7db3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7db8  brfalse  loc_7E63
0x7dbd  ldstr    aName// "Name"
0x7dc2  stloc.1
0x7dc3  ldstr    aPath_0// "Path"
0x7dc8  stloc.2
0x7dc9  ldarg.3
0x7dca  ldloc.1
0x7dcb  call     T0x2B000044
0x7dd0  brfalse.s loc_7E0A
0x7dd2  ldarg.3
0x7dd3  ldloc.2
0x7dd4  call     T0x2B000044
0x7dd9  brfalse.s loc_7E0A
0x7ddb  ldarg.2
0x7ddc  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x7de1  ldarg.2
0x7de2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x7de7  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x7dec  brtrue.s loc_7E0A
0x7dee  ldarg.0
0x7def  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Logger()
0x7df4  ldc.i4.1
0x7df5  ldstr    aInvalidPatchRe// "Invalid PATCH request, Path does not en"...
0x7dfa  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7dff  ldstr    aPathDoesNotEnd// "Path does not end with Name of catalog "...
0x7e04  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7e09  throw
0x7e0a  ldarg.3
0x7e0b  ldloc.1
0x7e0c  call     T0x2B000044
0x7e11  brfalse.s loc_7E4E
0x7e13  ldarg.3
0x7e14  ldloc.2
0x7e15  call     T0x2B000044
0x7e1a  brtrue.s loc_7E4E
0x7e1c  ldarg.2
0x7e1d  ldarg.2
0x7e1e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x7e23  ldc.i4.0
0x7e24  ldarg.2
0x7e25  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x7e2a  ldstr    asc_10432// "/"
0x7e2f  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string)
0x7e34  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7e39  ldstr    asc_10432// "/"
0x7e3e  ldarg.2
0x7e3f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x7e44  call     string [mscorlib]System.String::Concat(string, string, string)
0x7e49  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x7e4e  ldarg.0
0x7e4f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7e54  ldarg.0
0x7e55  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7e5a  ldloc.0
0x7e5b  ldarg.2
0x7e5c  ldarg.3
0x7e5d  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x7e62  ret
0x7e63  ldc.i4.0
0x7e64  ret
```
