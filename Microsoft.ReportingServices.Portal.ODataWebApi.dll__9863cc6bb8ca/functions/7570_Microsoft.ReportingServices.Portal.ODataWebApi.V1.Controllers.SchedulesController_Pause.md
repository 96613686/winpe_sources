# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Pause

- ea: `0x7570`
- end: `0x7592`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Pause`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e10`

## callees

- `0x7570`

## pseudocode

```c

```

## disassembly

```asm
0x7570  ldarg.0
0x7571  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x7576  ldarg.0
0x7577  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x757c  ldarg.1
0x757d  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::PauseSchedule(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x7582  brfalse.s loc_758B
0x7584  ldarg.0
0x7585  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::Ok()
0x758a  ret
0x758b  ldarg.0
0x758c  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::BadRequest()
0x7591  ret
```
