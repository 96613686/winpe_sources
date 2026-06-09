# Microsoft.BIServer.HostingEnvironment.Logger::FilePathFromTarget

- ea: `0x1320`
- end: `0x133c`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::FilePathFromTarget`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1140`
- `0x1650`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  callvirt instance class [NLog]NLog.Layouts.Layout [NLog]NLog.Targets.FileTarget::get_FileName()
0x1326  newobj   instance void [NLog]NLog.LogEventInfo::.ctor()
0x132b  dup
0x132c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1331  callvirt instance void [NLog]NLog.LogEventInfo::set_TimeStamp(valuetype [mscorlib]System.DateTime)
0x1336  callvirt instance string [NLog]NLog.Layouts.Layout::Render(class [NLog]NLog.LogEventInfo)
0x133b  ret
```
