# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::PutEntity

- ea: `0x8c30`
- end: `0x8c51`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::PutEntity`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x8c30`

## pseudocode

```c

```

## disassembly

```asm
0x8c30  ldarg.1
0x8c31  ldloca.s 0
0x8c33  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8c38  brfalse.s loc_8C4F
0x8c3a  ldarg.0
0x8c3b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8c40  ldarg.0
0x8c41  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8c46  ldloc.0
0x8c47  ldarg.2
0x8c48  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::UpdateSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription)
0x8c4d  ldc.i4.1
0x8c4e  ret
0x8c4f  ldc.i4.0
0x8c50  ret
```
