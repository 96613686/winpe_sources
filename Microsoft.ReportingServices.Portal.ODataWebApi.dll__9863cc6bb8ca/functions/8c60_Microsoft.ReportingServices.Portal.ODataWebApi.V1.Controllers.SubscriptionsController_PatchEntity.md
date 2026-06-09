# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::PatchEntity

- ea: `0x8c60`
- end: `0x8c82`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::PatchEntity`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5ee0`

## callees

- `0x8c60`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  ldarg.1
0x8c61  ldloca.s 0
0x8c63  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8c68  brfalse.s loc_8C80
0x8c6a  ldarg.0
0x8c6b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController::_subscriptionService
0x8c70  ldarg.0
0x8c71  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8c76  ldloc.0
0x8c77  ldarg.2
0x8c78  ldarg.3
0x8c79  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::PatchSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription, string[])
0x8c7e  ldc.i4.1
0x8c7f  ret
0x8c80  ldc.i4.0
0x8c81  ret
```
