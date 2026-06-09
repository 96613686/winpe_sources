# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::get_CurrentTraceFilePath

- ea: `0x680`
- end: `0x691`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::get_CurrentTraceFilePath`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x680`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldloca.s 0
0x682  call     bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::TryGetFileTargetName(string&)
0x687  brfalse.s loc_68B
0x689  ldloc.0
0x68a  ret
0x68b  ldsfld   string [mscorlib]System.String::Empty
0x690  ret
```
