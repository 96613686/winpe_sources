# Microsoft.BIServer.HostingEnvironment.Logger::Warning

- ea: `0x1590`
- end: `0x15aa`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Warning`
- size: `26`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xfe0`
- `0x1860`
- `0x18b0`
- `0x3f50`
- `0x4070`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x1590  ldarg.0
0x1591  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Warn
0x1596  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x159b  starg.s  0
0x159d  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x15a2  ldarg.0
0x15a3  ldarg.1
0x15a4  callvirt instance void [NLog]NLog.Logger::Warn(string, object[])
0x15a9  ret
```
