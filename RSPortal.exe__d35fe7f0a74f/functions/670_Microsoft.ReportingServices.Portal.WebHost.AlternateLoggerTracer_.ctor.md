# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::.ctor

- ea: `0x670`
- end: `0x67e`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d0`

## pseudocode

```c

```

## disassembly

```asm
0x670  ldarg.0
0x671  call     instance void [mscorlib]System.Object::.ctor()
0x676  ldarg.0
0x677  ldarg.1
0x678  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::_logger
0x67d  ret
```
