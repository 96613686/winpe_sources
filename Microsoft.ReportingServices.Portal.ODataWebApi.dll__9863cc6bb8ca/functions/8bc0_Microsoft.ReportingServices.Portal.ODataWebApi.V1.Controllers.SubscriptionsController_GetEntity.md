# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::GetEntity

- ea: `0x8bc0`
- end: `0x8bdf`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::GetEntity`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ea0`

## callees

- `0x8bc0`

## pseudocode

```c

```

## disassembly

```asm
0x8bc0  ldarg.1
0x8bc1  ldloca.s 0
0x8bc3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8bc8  brfalse.s loc_8BDD
0x8bca  ldarg.0
0x8bcb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8bd0  ldarg.0
0x8bd1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8bd6  ldloc.0
0x8bd7  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::GetSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x8bdc  ret
0x8bdd  ldnull
0x8bde  ret
```
