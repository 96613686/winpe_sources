# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_0

- ea: `0x780`
- end: `0x793`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x780  ldstr    a01// "{0}|{1}"
0x785  ldarg.1
0x786  ldarg.2
0x787  call     string [mscorlib]System.String::Format(string, object, object)
0x78c  ldarg.3
0x78d  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x792  ret
```
