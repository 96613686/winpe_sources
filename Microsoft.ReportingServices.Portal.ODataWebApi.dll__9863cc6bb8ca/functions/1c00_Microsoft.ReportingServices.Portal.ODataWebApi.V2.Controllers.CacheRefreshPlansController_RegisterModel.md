# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::RegisterModel

- ea: `0x1c00`
- end: `0x1c2a`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController::RegisterModel`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x1c01`: `CacheRefreshPlans`
- `0x1c1e`: `CacheRefreshPlanHistory`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  ldarg.0
0x1c01  ldstr    aCacherefreshpl// "CacheRefreshPlans"
0x1c06  callvirt T0x2B000037
0x1c0b  pop
0x1c0c  ldarg.0
0x1c0d  callvirt T0x2B000038
0x1c12  ldstr    aExecute// "Execute"
0x1c17  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan>::Action(string)
0x1c1c  pop
0x1c1d  ldarg.0
0x1c1e  ldstr    aCacherefreshpl_0// "CacheRefreshPlanHistory"
0x1c23  callvirt T0x2B000039
0x1c28  pop
0x1c29  ret
```
