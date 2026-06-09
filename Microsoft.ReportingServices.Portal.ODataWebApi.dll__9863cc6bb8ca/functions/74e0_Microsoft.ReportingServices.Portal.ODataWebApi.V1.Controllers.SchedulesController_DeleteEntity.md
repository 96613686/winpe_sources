# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::DeleteEntity

- ea: `0x74e0`
- end: `0x74ff`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::DeleteEntity`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5dc0`

## callees

- `0x74e0`
- `0x76a0`

## pseudocode

```c

```

## disassembly

```asm
0x74e0  ldarg.1
0x74e1  ldloca.s 0
0x74e3  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::TryParseGuid(string key, [out] valuetype [mscorlib]System.Guid& gKey)
0x74e8  brfalse.s loc_74FD
0x74ea  ldarg.0
0x74eb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x74f0  ldarg.0
0x74f1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x74f6  ldloc.0
0x74f7  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::DeleteSchedule(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x74fc  ret
0x74fd  ldc.i4.0
0x74fe  ret
```
