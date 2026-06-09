# Microsoft.BIServer.HostingEnvironment.Logger::Trace

- ea: `0x1430`
- end: `0x144a`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Trace`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1860`
- `0x18b0`
- `0x3f50`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x1430  ldarg.0
0x1431  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Trace
0x1436  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x143b  starg.s  0
0x143d  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x1442  ldarg.0
0x1443  ldarg.1
0x1444  callvirt instance void [NLog]NLog.Logger::Trace(string, object[])
0x1449  ret
```
