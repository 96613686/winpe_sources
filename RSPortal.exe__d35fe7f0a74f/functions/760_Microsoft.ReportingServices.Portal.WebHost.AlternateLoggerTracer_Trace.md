# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace

- ea: `0x760`
- end: `0x777`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::Trace`
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
0x760  ldstr    a01// "{0}|{1}"
0x765  ldarg.1
0x766  ldarg.2
0x767  call     string [mscorlib]System.String::Format(string, object, object)
0x76c  call     T0x2B000001
0x771  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x776  ret
```
