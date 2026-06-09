# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_2

- ea: `0x7c0`
- end: `0x7d4`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace_2`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  ldstr    a01// "{0}|{1}"
0x7c5  ldarg.2
0x7c6  ldarg.3
0x7c7  call     string [mscorlib]System.String::Format(string, object, object)
0x7cc  ldarg.s  4
0x7ce  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x7d3  ret
```
