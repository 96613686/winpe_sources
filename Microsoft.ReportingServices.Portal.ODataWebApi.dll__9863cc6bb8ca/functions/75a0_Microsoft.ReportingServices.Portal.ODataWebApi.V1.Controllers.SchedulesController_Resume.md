# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Resume

- ea: `0x75a0`
- end: `0x75c2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::Resume`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e20`

## callees

- `0x75a0`

## pseudocode

```c

```

## disassembly

```asm
0x75a0  ldarg.0
0x75a1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::_systemService
0x75a6  ldarg.0
0x75a7  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x75ac  ldarg.1
0x75ad  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ResumeSchedule(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x75b2  brfalse.s loc_75BB
0x75b4  ldarg.0
0x75b5  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::Ok()
0x75ba  ret
0x75bb  ldarg.0
0x75bc  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule>::BadRequest()
0x75c1  ret
```
