# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::TraceWithDetails

- ea: `0x800`
- end: `0x81b`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::TraceWithDetails`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldarg.0
0x801  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::_logger
0x806  ldarg.1
0x807  ldstr    a012// "{0}|{1}|{2}"
0x80c  ldarg.2
0x80d  ldarg.3
0x80e  ldarg.s  4
0x810  call     string [mscorlib]System.String::Format(string, object, object, object)
0x815  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x81a  ret
```
