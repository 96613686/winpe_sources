# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::PutEntity

- ea: `0x7520`
- end: `0x7540`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::PutEntity`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5de0`

## callees

- `0x7520`
- `0x76a0`

## pseudocode

```c

```

## disassembly

```asm
0x7520  ldarg.1
0x7521  ldloca.s 0
0x7523  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::TryParseGuid(string key, [out] valuetype [mscorlib]System.Guid& gKey)
0x7528  brfalse.s loc_753E
0x752a  ldarg.0
0x752b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x7530  ldarg.0
0x7531  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7536  ldloc.0
0x7537  ldarg.2
0x7538  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::UpdateSchedule(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule)
0x753d  ret
0x753e  ldc.i4.0
0x753f  ret
```
