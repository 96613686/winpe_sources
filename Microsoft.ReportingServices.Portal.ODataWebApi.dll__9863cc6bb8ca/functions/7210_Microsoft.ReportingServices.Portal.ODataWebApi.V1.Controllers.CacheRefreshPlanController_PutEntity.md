# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::PutEntity

- ea: `0x7210`
- end: `0x7231`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::PutEntity`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c70`

## callees

- `0x7210`

## pseudocode

```c

```

## disassembly

```asm
0x7210  ldarg.1
0x7211  ldloca.s 0
0x7213  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7218  brfalse.s loc_722F
0x721a  ldarg.0
0x721b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_subscriptionService
0x7220  ldarg.0
0x7221  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7226  ldloc.0
0x7227  ldarg.2
0x7228  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::UpdateCacheRefreshPlan(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan)
0x722d  ldc.i4.1
0x722e  ret
0x722f  ldc.i4.0
0x7230  ret
```
