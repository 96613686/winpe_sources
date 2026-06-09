# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::GetSingleton

- ea: `0x70d0`
- end: `0x7112`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::GetSingleton`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6060`

## callees

- `0x70d0`

## pseudocode

```c

```

## disassembly

```asm
0x70d0  ldarg.0
0x70d1  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x70d6  brfalse.s loc_7107
0x70d8  ldarg.0
0x70d9  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x70de  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x70e3  brfalse.s loc_7107
0x70e5  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Telemetry::.ctor()
0x70ea  dup
0x70eb  ldarg.0
0x70ec  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::_telemetryService
0x70f1  ldarg.0
0x70f2  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x70f7  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x70fc  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService::GetSystemProperties(class [mscorlib]System.Security.Principal.IIdentity)
0x7101  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Telemetry::set_Properties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData)
0x7106  ret
0x7107  ldstr    aNoIdentityFoun// "No Identity found"
0x710c  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x7111  throw
```
