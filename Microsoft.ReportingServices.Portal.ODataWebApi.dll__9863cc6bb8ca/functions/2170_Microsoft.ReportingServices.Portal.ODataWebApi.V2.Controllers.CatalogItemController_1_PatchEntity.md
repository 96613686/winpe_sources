# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::PatchEntity

- ea: `0x2170`
- end: `0x224f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::PatchEntity`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2170`

## string_xrefs

- `0x21c6`: `Invalid PATCH request, Path does not end with Name of catalog item.`
- `0x21d0`: `Path does not end with Name of catalog item.`

## pseudocode

```c

```

## disassembly

```asm
0x2170  ldarg.0
0x2171  ldarg.1
0x2172  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::ThrowIfWrongType(string)
0x2177  ldarg.1
0x2178  ldloca.s 0
0x217a  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x217f  brfalse  loc_224D
0x2184  ldstr    aName// "Name"
0x2189  stloc.1
0x218a  ldstr    aPath_0// "Path"
0x218f  stloc.2
0x2190  ldarg.3
0x2191  ldloc.1
0x2192  call     T0x2B000044
0x2197  brfalse.s loc_21DB
0x2199  ldarg.3
0x219a  ldloc.2
0x219b  call     T0x2B000044
0x21a0  brfalse.s loc_21DB
0x21a2  ldarg.2
0x21a3  box      var<u1>
0x21a8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x21ad  ldarg.2
0x21ae  box      var<u1>
0x21b3  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x21b8  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x21bd  brtrue.s loc_21DB
0x21bf  ldarg.0
0x21c0  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0x21c5  ldc.i4.1
0x21c6  ldstr    aInvalidPatchRe// "Invalid PATCH request, Path does not en"...
0x21cb  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x21d0  ldstr    aPathDoesNotEnd// "Path does not end with Name of catalog "...
0x21d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x21da  throw
0x21db  ldarg.3
0x21dc  ldloc.1
0x21dd  call     T0x2B000044
0x21e2  brfalse.s loc_2233
0x21e4  ldarg.3
0x21e5  ldloc.2
0x21e6  call     T0x2B000044
0x21eb  brtrue.s loc_2233
0x21ed  ldarg.2
0x21ee  box      var<u1>
0x21f3  ldarg.2
0x21f4  box      var<u1>
0x21f9  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x21fe  ldc.i4.0
0x21ff  ldarg.2
0x2200  box      var<u1>
0x2205  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x220a  ldstr    asc_10432// "/"
0x220f  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string)
0x2214  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2219  ldstr    asc_10432// "/"
0x221e  ldarg.2
0x221f  box      var<u1>
0x2224  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2229  call     string [mscorlib]System.String::Concat(string, string, string)
0x222e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x2233  ldarg.0
0x2234  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x2239  ldarg.0
0x223a  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x223f  ldloc.0
0x2240  ldarg.2
0x2241  box      var<u1>
0x2246  ldarg.3
0x2247  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x224c  ret
0x224d  ldc.i4.0
0x224e  ret
```
