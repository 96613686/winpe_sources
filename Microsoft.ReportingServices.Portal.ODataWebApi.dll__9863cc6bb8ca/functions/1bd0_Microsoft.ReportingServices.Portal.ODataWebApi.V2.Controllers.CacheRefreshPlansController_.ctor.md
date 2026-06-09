# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::.ctor

- ea: `0x1bd0`
- end: `0x1bee`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x7130`
- `0x7140`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldarg.1
0x1bd2  ldarg.s  4
0x1bd4  ldarg.2
0x1bd5  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService subscriptionService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x1bda  ldarg.0
0x1bdb  ldarg.0
0x1bdc  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::get_SubscriptionService()
0x1be1  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::_subscriptionService
0x1be6  ldarg.0
0x1be7  ldarg.3
0x1be8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::_catalogRepository
0x1bed  ret
```
