# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::TraceException

- ea: `0x7e0`
- end: `0x7f7`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::TraceException`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldstr    a01// "{0}|{1}"
0x7e5  ldarg.2
0x7e6  ldarg.3
0x7e7  call     string [mscorlib]System.String::Format(string, object, object)
0x7ec  call     T0x2B000001
0x7f1  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x7f6  ret
```
