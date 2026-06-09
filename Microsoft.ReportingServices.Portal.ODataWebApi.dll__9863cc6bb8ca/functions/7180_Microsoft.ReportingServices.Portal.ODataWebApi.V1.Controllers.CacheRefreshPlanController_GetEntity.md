# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::GetEntity

- ea: `0x7180`
- end: `0x71c4`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::GetEntity`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c40`

## callees

- `0x7180`

## pseudocode

```c

```

## disassembly

```asm
0x7180  ldarg.1
0x7181  ldloca.s 0
0x7183  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7188  brfalse.s loc_71C2
0x718a  ldarg.0
0x718b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_subscriptionService
0x7190  ldarg.0
0x7191  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7196  ldloc.0
0x7197  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService::GetCacheRefreshPlan(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x719c  stloc.1
0x719d  ldloc.1
0x719e  ldarg.0
0x719f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController::_systemService
0x71a4  ldarg.0
0x71a5  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x71aa  ldloc.1
0x71ab  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::get_Schedule()
0x71b0  ldarg.0
0x71b1  call     instance int32 class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan>::GetUtcOffsetInMinutes()
0x71b6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::PopulateScheduleDescription(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference, int32)
0x71bb  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_ScheduleDescription(string)
0x71c0  ldloc.1
0x71c1  ret
0x71c2  ldnull
0x71c3  ret
```
