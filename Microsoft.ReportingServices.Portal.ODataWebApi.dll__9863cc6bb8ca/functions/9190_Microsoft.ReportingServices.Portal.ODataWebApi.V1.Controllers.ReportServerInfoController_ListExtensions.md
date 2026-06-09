# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::ListExtensions

- ea: `0x9190`
- end: `0x91a3`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::ListExtensions`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8de0`
- `0x8df0`
- `0x8e00`
- `0x8e10`

## pseudocode

```c

```

## disassembly

```asm
0x9190  ldarg.0
0x9191  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0x9196  ldarg.0
0x9197  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x919c  ldarg.1
0x919d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ListExtensions(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionType)
0x91a2  ret
```
