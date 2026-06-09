# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::.ctor

- ea: `0x2a60`
- end: `0x2ac8`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::.ctor`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x76d0`
- `0x76e0`
- `0x7700`
- `0xcde0`

## pseudocode

```c

```

## disassembly

```asm
0x2a60  ldarg.0
0x2a61  ldarg.1
0x2a62  ldarg.2
0x2a63  ldarg.s  5
0x2a65  ldarg.s  6
0x2a67  ldarg.3
0x2a68  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService dataService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigurationManager, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x2a6d  ldarg.0
0x2a6e  ldarg.0
0x2a6f  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogRepository()
0x2a74  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2a79  ldarg.0
0x2a7a  ldarg.0
0x2a7b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_DataService()
0x2a80  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_dataService
0x2a85  ldarg.0
0x2a86  ldarg.0
0x2a87  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Logger()
0x2a8c  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_logger
0x2a91  ldarg.0
0x2a92  ldarg.s  4
0x2a94  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_encryptionService
0x2a99  ldarg.0
0x2a9a  ldarg.s  5
0x2a9c  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_systemService
0x2aa1  ldarg.0
0x2aa2  ldarg.s  6
0x2aa4  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_portalConfigurationManager
0x2aa9  ldarg.0
0x2aaa  ldarg.0
0x2aab  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2ab0  ldarg.0
0x2ab1  ldarg.0
0x2ab2  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_portalConfigurationManager
0x2ab7  ldarg.0
0x2ab8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_logger
0x2abd  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController catalogItemController, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigurationManager, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x2ac2  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_powerBIReportsControllerHelper
0x2ac7  ret
```
