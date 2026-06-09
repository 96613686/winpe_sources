# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::GetLoggerTraceLevel

- ea: `0x720`
- end: `0x72d`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::GetLoggerTraceLevel`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x730`

## callees

- `0x720`

## pseudocode

```c

```

## disassembly

```asm
0x720  ldc.i4.3
0x721  stloc.0
0x722  call     bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::IsDebugEnabled()
0x727  brfalse.s loc_72B
0x729  ldc.i4.4
0x72a  stloc.0
0x72b  ldloc.0
0x72c  ret
```
