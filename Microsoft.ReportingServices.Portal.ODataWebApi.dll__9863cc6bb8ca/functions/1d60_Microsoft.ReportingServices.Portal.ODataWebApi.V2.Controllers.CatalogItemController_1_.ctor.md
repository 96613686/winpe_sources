# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::.ctor

- ea: `0x1d60`
- end: `0x1e20`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::.ctor`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1d60`

## string_xrefs

- `0x1d79`: `dataService`
- `0x1d87`: `systemService`
- `0x1d96`: `portalConfigurationManager`

## pseudocode

```c

```

## disassembly

```asm
0x1d60  ldarg.0
0x1d61  ldarg.s  5
0x1d63  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x1d68  ldarg.1
0x1d69  brtrue.s loc_1D76
0x1d6b  ldstr    aCatalogreposit// "catalogRepository"
0x1d70  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d75  throw
0x1d76  ldarg.2
0x1d77  brtrue.s loc_1D84
0x1d79  ldstr    aDataservice// "dataService"
0x1d7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d83  throw
0x1d84  ldarg.3
0x1d85  brtrue.s loc_1D92
0x1d87  ldstr    aSystemservice// "systemService"
0x1d8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d91  throw
0x1d92  ldarg.s  4
0x1d94  brtrue.s loc_1DA1
0x1d96  ldstr    aPortalconfigur// "portalConfigurationManager"
0x1d9b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1da0  throw
0x1da1  ldarg.s  5
0x1da3  brtrue.s loc_1DB0
0x1da5  ldstr    aLogger// "logger"
0x1daa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1daf  throw
0x1db0  ldarg.0
0x1db1  call     string [mscorlib]System.IO.Path::GetTempPath()
0x1db6  ldstr    aCatalogupload// "CatalogUpload_"
0x1dbb  ldc.i4   0x7FFFFFFF
0x1dc0  conv.i8
0x1dc1  ldsfld   int32 class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::DeleteTempFileDays
0x1dc6  conv.r8
0x1dc7  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0x1dcc  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader::.ctor(string, string, int64, valuetype [mscorlib]System.TimeSpan)
0x1dd1  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_uploader
0x1dd6  ldarg.0
0x1dd7  ldarg.1
0x1dd8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x1ddd  ldarg.0
0x1dde  ldarg.2
0x1ddf  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_dataService
0x1de4  ldarg.0
0x1de5  ldarg.3
0x1de6  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_systemService
0x1deb  ldarg.0
0x1dec  ldarg.s  4
0x1dee  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_portalConfigurationManager
0x1df3  ldarg.0
0x1df4  ldarg.s  5
0x1df6  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_logger
0x1dfb  ldarg.0
0x1dfc  ldarg.1
0x1dfd  ldarg.0
0x1dfe  ldarg.3
0x1dff  ldarg.s  4
0x1e01  ldarg.s  5
0x1e03  newobj   instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>, !!T0, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x1e08  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogItemControllerHelper
0x1e0d  ldarg.0
0x1e0e  ldarg.s  4
0x1e10  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x1e15  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_FileSizeRestrictions()
0x1e1a  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::set_FileSizeRestrictions(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions)
0x1e1f  ret
```
