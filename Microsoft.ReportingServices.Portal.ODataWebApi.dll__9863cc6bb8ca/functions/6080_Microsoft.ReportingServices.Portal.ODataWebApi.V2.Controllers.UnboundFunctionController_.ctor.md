# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::.ctor

- ea: `0x6080`
- end: `0x60be`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::.ctor`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x9620`
- `0x9630`
- `0x9640`
- `0x9650`

## pseudocode

```c

```

## disassembly

```asm
0x6080  ldarg.0
0x6081  ldarg.1
0x6082  ldarg.2
0x6083  ldarg.3
0x6084  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService systemResourceService)
0x6089  ldarg.0
0x608a  ldarg.0
0x608b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::get_CatalogRepository()
0x6090  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_catalogRepository
0x6095  ldarg.0
0x6096  ldarg.0
0x6097  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::get_SystemService()
0x609c  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemService
0x60a1  ldarg.0
0x60a2  ldarg.0
0x60a3  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::get_SystemResourceService()
0x60a8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_systemResourceService
0x60ad  ldarg.0
0x60ae  ldarg.s  4
0x60b0  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_logger
0x60b5  ldarg.0
0x60b6  ldarg.s  5
0x60b8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::_portalConfigurationManager
0x60bd  ret
```
