# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::DeleteEntity

- ea: `0x95d0`
- end: `0x95ef`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::DeleteEntity`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6000`

## callees

- `0x95d0`

## pseudocode

```c

```

## disassembly

```asm
0x95d0  ldarg.1
0x95d1  ldloca.s 0
0x95d3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x95d8  brfalse.s loc_95ED
0x95da  ldarg.0
0x95db  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::_systemResourceService
0x95e0  ldarg.0
0x95e1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x95e6  ldloc.0
0x95e7  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService::DeleteSystemResource(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x95ec  ret
0x95ed  ldc.i4.0
0x95ee  ret
```
