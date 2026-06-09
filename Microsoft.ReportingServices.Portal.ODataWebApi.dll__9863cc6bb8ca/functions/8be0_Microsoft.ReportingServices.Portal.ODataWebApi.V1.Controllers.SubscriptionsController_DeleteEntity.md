# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::DeleteEntity

- ea: `0x8be0`
- end: `0x8c00`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::DeleteEntity`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5eb0`

## callees

- `0x8be0`

## pseudocode

```c

```

## disassembly

```asm
0x8be0  ldarg.1
0x8be1  ldloca.s 0
0x8be3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8be8  brfalse.s loc_8BFE
0x8bea  ldarg.0
0x8beb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8bf0  ldarg.0
0x8bf1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8bf6  ldloc.0
0x8bf7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::DeleteSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x8bfc  ldc.i4.1
0x8bfd  ret
0x8bfe  ldc.i4.0
0x8bff  ret
```
