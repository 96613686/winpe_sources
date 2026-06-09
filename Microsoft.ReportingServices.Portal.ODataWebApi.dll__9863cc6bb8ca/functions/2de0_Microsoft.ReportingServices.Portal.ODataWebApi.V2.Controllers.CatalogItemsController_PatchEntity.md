# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::PatchEntity

- ea: `0x2de0`
- end: `0x2ed1`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::PatchEntity`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x2de0`
- `0x76f0`

## string_xrefs

- `0x2e48`: `Invalid PATCH request, Path does not end with Name of catalog item.`
- `0x2e52`: `Path does not end with Name of catalog item.`

## pseudocode

```c

```

## disassembly

```asm
0x2de0  ldarg.0
0x2de1  ldarg.2
0x2de2  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::ValidatePbiFile(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem entity)
0x2de7  ldarg.0
0x2de8  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogItemControllerHelper()
0x2ded  ldarg.1
0x2dee  ldloca.s 0
0x2df0  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::IsRequestByPath(string, string&)
0x2df5  stloc.1
0x2df6  ldloca.s 2
0x2df8  initobj  [mscorlib]System.Guid
0x2dfe  ldloc.1
0x2dff  brtrue.s loc_2E0E
0x2e01  ldarg.1
0x2e02  ldloca.s 2
0x2e04  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2e09  brfalse  loc_2ECF
0x2e0e  ldstr    aName// "Name"
0x2e13  stloc.3
0x2e14  ldstr    aPath_0// "Path"
0x2e19  stloc.s  4
0x2e1b  ldarg.3
0x2e1c  ldloc.3
0x2e1d  call     T0x2B000044
0x2e22  brfalse.s loc_2E5D
0x2e24  ldarg.3
0x2e25  ldloc.s  4
0x2e27  call     T0x2B000044
0x2e2c  brfalse.s loc_2E5D
0x2e2e  ldarg.2
0x2e2f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x2e34  ldarg.2
0x2e35  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2e3a  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x2e3f  brtrue.s loc_2E5D
0x2e41  ldarg.0
0x2e42  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Logger()
0x2e47  ldc.i4.1
0x2e48  ldstr    aInvalidPatchRe// "Invalid PATCH request, Path does not en"...
0x2e4d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2e52  ldstr    aPathDoesNotEnd// "Path does not end with Name of catalog "...
0x2e57  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2e5c  throw
0x2e5d  ldarg.3
0x2e5e  ldloc.3
0x2e5f  call     T0x2B000044
0x2e64  brfalse.s loc_2EA2
0x2e66  ldarg.3
0x2e67  ldloc.s  4
0x2e69  call     T0x2B000044
0x2e6e  brtrue.s loc_2EA2
0x2e70  ldarg.2
0x2e71  ldarg.2
0x2e72  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x2e77  ldc.i4.0
0x2e78  ldarg.2
0x2e79  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x2e7e  ldstr    asc_10432// "/"
0x2e83  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string)
0x2e88  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2e8d  ldstr    asc_10432// "/"
0x2e92  ldarg.2
0x2e93  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2e98  call     string [mscorlib]System.String::Concat(string, string, string)
0x2e9d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x2ea2  ldloc.1
0x2ea3  brtrue.s loc_2EBA
0x2ea5  ldarg.0
0x2ea6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2eab  ldarg.0
0x2eac  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2eb1  ldloc.2
0x2eb2  ldarg.2
0x2eb3  ldarg.3
0x2eb4  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x2eb9  ret
0x2eba  ldarg.0
0x2ebb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2ec0  ldarg.0
0x2ec1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2ec6  ldloc.0
0x2ec7  ldarg.2
0x2ec8  ldarg.3
0x2ec9  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::Update(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, string[])
0x2ece  ret
0x2ecf  ldc.i4.0
0x2ed0  ret
```
