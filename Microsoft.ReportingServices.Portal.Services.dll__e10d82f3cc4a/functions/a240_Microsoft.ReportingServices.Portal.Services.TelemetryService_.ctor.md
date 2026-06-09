# Microsoft.ReportingServices.Portal.Services.TelemetryService::.ctor

- ea: `0xa240`
- end: `0xa286`
- name: `Microsoft.ReportingServices.Portal.Services.TelemetryService::.ctor`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa240`

## string_xrefs

- `0xa265`: `systemService`
- `0xa257`: `configManager`

## pseudocode

```c

```

## disassembly

```asm
0xa240  ldarg.0
0xa241  call     instance void [mscorlib]System.Object::.ctor()
0xa246  ldarg.1
0xa247  brtrue.s loc_A254
0xa249  ldstr    aFactory// "factory"
0xa24e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa253  throw
0xa254  ldarg.2
0xa255  brtrue.s loc_A262
0xa257  ldstr    aConfigmanager// "configManager"
0xa25c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa261  throw
0xa262  ldarg.3
0xa263  brtrue.s loc_A270
0xa265  ldstr    aSystemservice// "systemService"
0xa26a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa26f  throw
0xa270  ldarg.0
0xa271  ldarg.1
0xa272  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryConfigurationFactory Microsoft.ReportingServices.Portal.Services.TelemetryService::_telemetryFactory
0xa277  ldarg.0
0xa278  ldarg.2
0xa279  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.TelemetryService::_configManager
0xa27e  ldarg.0
0xa27f  ldarg.3
0xa280  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Services.TelemetryService::_systemService
0xa285  ret
```
