# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::.ctor

- ea: `0x7700`
- end: `0x7788`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::.ctor`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2a60`

## callees

- `0x7700`

## string_xrefs

- `0x7719`: `dataService`
- `0x7727`: `systemService`
- `0x7736`: `portalConfigurationManager`

## pseudocode

```c

```

## disassembly

```asm
0x7700  ldarg.0
0x7701  ldarg.s  5
0x7703  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x7708  ldarg.1
0x7709  brtrue.s loc_7716
0x770b  ldstr    aCatalogreposit// "catalogRepository"
0x7710  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7715  throw
0x7716  ldarg.2
0x7717  brtrue.s loc_7724
0x7719  ldstr    aDataservice// "dataService"
0x771e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7723  throw
0x7724  ldarg.3
0x7725  brtrue.s loc_7732
0x7727  ldstr    aSystemservice// "systemService"
0x772c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7731  throw
0x7732  ldarg.s  4
0x7734  brtrue.s loc_7741
0x7736  ldstr    aPortalconfigur// "portalConfigurationManager"
0x773b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7740  throw
0x7741  ldarg.s  5
0x7743  brtrue.s loc_7750
0x7745  ldstr    aLogger// "logger"
0x774a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x774f  throw
0x7750  ldarg.0
0x7751  ldarg.1
0x7752  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7757  ldarg.0
0x7758  ldarg.2
0x7759  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_dataService
0x775e  ldarg.0
0x775f  ldarg.3
0x7760  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_systemService
0x7765  ldarg.0
0x7766  ldarg.s  4
0x7768  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_portalConfigurationManager
0x776d  ldarg.0
0x776e  ldarg.s  5
0x7770  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_logger
0x7775  ldarg.0
0x7776  ldarg.1
0x7777  ldarg.0
0x7778  ldarg.3
0x7779  ldarg.s  4
0x777b  ldarg.s  5
0x777d  newobj   instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>, !!T0, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x7782  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogItemControllerHelper
0x7787  ret
```
