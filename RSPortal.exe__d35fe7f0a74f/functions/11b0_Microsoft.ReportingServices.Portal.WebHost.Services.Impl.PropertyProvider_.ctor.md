# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::.ctor

- ea: `0x11b0`
- end: `0x11be`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  call     instance void [mscorlib]System.Object::.ctor()
0x11b6  ldarg.0
0x11b7  ldarg.1
0x11b8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::_portalConfigManager
0x11bd  ret
```
