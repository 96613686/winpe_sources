# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::DeleteEntity

- ea: `0x71d0`
- end: `0x71f0`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::DeleteEntity`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c50`

## callees

- `0x71d0`

## pseudocode

```c

```

## disassembly

```asm
0x71d0  ldarg.1
0x71d1  ldloca.s 0
0x71d3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x71d8  brfalse.s loc_71EE
0x71da  ldarg.0
0x71db  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_subscriptionService
0x71e0  ldarg.0
0x71e1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x71e6  ldloc.0
0x71e7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::DeleteCacheRefreshPlan(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x71ec  ldc.i4.1
0x71ed  ret
0x71ee  ldc.i4.0
0x71ef  ret
```
