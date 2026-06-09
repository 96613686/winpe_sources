# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::.ctor

- ea: `0x8b30`
- end: `0x8b62`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e60`

## callees

- `0x8b30`

## string_xrefs

- `0x8b48`: `systemService`
- `0x8b3a`: `subscriptionService`

## pseudocode

```c

```

## disassembly

```asm
0x8b30  ldarg.0
0x8b31  ldarg.2
0x8b32  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x8b37  ldarg.1
0x8b38  brtrue.s loc_8B45
0x8b3a  ldstr    aSubscriptionse// "subscriptionService"
0x8b3f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8b44  throw
0x8b45  ldarg.3
0x8b46  brtrue.s loc_8B53
0x8b48  ldstr    aSystemservice// "systemService"
0x8b4d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8b52  throw
0x8b53  ldarg.0
0x8b54  ldarg.3
0x8b55  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_systemService
0x8b5a  ldarg.0
0x8b5b  ldarg.1
0x8b5c  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8b61  ret
```
