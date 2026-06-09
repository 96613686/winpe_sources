# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_1

- ea: `0x7a0`
- end: `0x7b9`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_1`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x700`
- `0x710`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::_logger
0x7a6  ldarg.1
0x7a7  ldstr    a01// "{0}|{1}"
0x7ac  ldarg.2
0x7ad  ldarg.3
0x7ae  call     string [mscorlib]System.String::Format(string, object, object)
0x7b3  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7b8  ret
```
