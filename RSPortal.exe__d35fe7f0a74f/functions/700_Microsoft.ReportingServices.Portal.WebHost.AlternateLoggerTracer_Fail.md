# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Fail

- ea: `0x700`
- end: `0x70e`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Fail`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  ldc.i4.1
0x702  ldarg.1
0x703  ldstr    aFail// "Fail"
0x708  call     instance void Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string componentName, string message)
0x70d  ret
```
