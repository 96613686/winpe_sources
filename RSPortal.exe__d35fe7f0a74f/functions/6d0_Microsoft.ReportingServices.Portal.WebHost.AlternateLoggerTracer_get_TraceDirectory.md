# Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::get_TraceDirectory

- ea: `0x6d0`
- end: `0x6e6`
- name: `Microsoft.ReportingServices.Portal.WebHost.AlternateLoggerTracer::get_TraceDirectory`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x6d0`

## pseudocode

```c

```

## disassembly

```asm
0x6d0  ldloca.s 0
0x6d2  call     bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::TryGetFileTargetName(string&)
0x6d7  brfalse.s loc_6E0
0x6d9  ldloc.0
0x6da  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x6df  ret
0x6e0  ldsfld   string [mscorlib]System.String::Empty
0x6e5  ret
```
