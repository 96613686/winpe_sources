# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SubscriptionsController::.ctor

- ea: `0x5e60`
- end: `0x5e82`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SubscriptionsController::.ctor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x8b10`
- `0x8b20`
- `0x8b30`

## pseudocode

```c

```

## disassembly

```asm
0x5e60  ldarg.0
0x5e61  ldarg.1
0x5e62  ldarg.2
0x5e63  ldarg.3
0x5e64  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService subscriptionService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x5e69  ldarg.0
0x5e6a  ldarg.0
0x5e6b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::get_SubscriptionService()
0x5e70  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SubscriptionsController::_subscriptionService
0x5e75  ldarg.0
0x5e76  ldarg.0
0x5e77  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::get_SystemService()
0x5e7c  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SubscriptionsController::_systemService
0x5e81  ret
```
