# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::GetDefaultTraceLevel

- ea: `0x730`
- end: `0x745`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::GetDefaultTraceLevel`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x720`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldarg.0
0x731  call     instance valuetype [System]System.Diagnostics.TraceLevel Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::GetLoggerTraceLevel()
0x736  stloc.0
0x737  ldloca.s 0
0x739  constrained. [System]System.Diagnostics.TraceLevel
0x73f  callvirt instance string [mscorlib]System.Object::ToString()
0x744  ret
```
