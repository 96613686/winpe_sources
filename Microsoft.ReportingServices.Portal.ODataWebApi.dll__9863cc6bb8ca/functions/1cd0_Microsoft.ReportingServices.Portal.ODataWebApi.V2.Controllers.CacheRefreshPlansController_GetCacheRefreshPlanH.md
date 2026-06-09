# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::GetCacheRefreshPlanHistory

- ea: `0x1cd0`
- end: `0x1cfc`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::GetCacheRefreshPlanHistory`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1bf0`
- `0x1cd0`

## pseudocode

```c

```

## disassembly

```asm
0x1cd0  ldsfld   string [mscorlib]System.String::Empty
0x1cd5  pop
0x1cd6  ldarg.1
0x1cd7  ldloca.s 0
0x1cd9  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1cde  brtrue.s loc_1CE7
0x1ce0  ldarg.0
0x1ce1  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan>::NotFound()
0x1ce6  ret
0x1ce7  ldarg.0
0x1ce8  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::get_CatalogRepository()
0x1ced  ldloc.0
0x1cee  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.SubscriptionHistory> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetSubscriptionsHistory(valuetype [mscorlib]System.Guid)
0x1cf3  stloc.1
0x1cf4  ldarg.0
0x1cf5  ldloc.1
0x1cf6  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan>::CreateOk(object)
0x1cfb  ret
```
