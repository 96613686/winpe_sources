# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::.ctor

- ea: `0x70b0`
- end: `0x70cd`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6040`

## callees

- `0x70b0`

## string_xrefs

- `0x70ba`: `telemetryService`

## pseudocode

```c

```

## disassembly

```asm
0x70b0  ldarg.0
0x70b1  ldarg.1
0x70b2  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Telemetry>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x70b7  ldarg.2
0x70b8  brtrue.s loc_70C5
0x70ba  ldstr    aTelemetryservi// "telemetryService"
0x70bf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x70c4  throw
0x70c5  ldarg.0
0x70c6  ldarg.2
0x70c7  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController::_telemetryService
0x70cc  ret
```
