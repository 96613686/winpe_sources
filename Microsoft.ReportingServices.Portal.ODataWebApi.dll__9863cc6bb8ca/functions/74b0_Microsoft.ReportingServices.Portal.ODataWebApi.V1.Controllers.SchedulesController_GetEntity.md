# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::GetEntity

- ea: `0x74b0`
- end: `0x74d5`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::GetEntity`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5db0`

## callees

- `0x74b0`
- `0x76a0`

## pseudocode

```c

```

## disassembly

```asm
0x74b0  ldarg.1
0x74b1  ldloca.s 0
0x74b3  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::TryParseGuid(string key, [out] valuetype [mscorlib]System.Guid& gKey)
0x74b8  brfalse.s loc_74D3
0x74ba  ldarg.0
0x74bb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x74c0  ldarg.0
0x74c1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x74c6  ldloc.0
0x74c7  ldarg.0
0x74c8  call     instance int32 class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::GetUtcOffsetInMinutes()
0x74cd  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::GetSchedule(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, int32)
0x74d2  ret
0x74d3  ldnull
0x74d4  ret
```
