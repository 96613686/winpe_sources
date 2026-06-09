# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::.ctor

- ea: `0x7140`
- end: `0x7164`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bd0`

## callees

- `0x7140`

## string_xrefs

- `0x714a`: `subscriptionService`

## pseudocode

```c

```

## disassembly

```asm
0x7140  ldarg.0
0x7141  ldarg.3
0x7142  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x7147  ldarg.1
0x7148  brtrue.s loc_7155
0x714a  ldstr    aSubscriptionse// "subscriptionService"
0x714f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7154  throw
0x7155  ldarg.0
0x7156  ldarg.1
0x7157  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_subscriptionService
0x715c  ldarg.0
0x715d  ldarg.2
0x715e  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_systemService
0x7163  ret
```
