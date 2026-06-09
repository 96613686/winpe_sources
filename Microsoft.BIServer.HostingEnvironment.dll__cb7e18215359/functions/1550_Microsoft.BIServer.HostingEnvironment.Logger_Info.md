# Microsoft.BIServer.HostingEnvironment.Logger::Info

- ea: `0x1550`
- end: `0x156a`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Info`
- size: `26`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xea0`
- `0xfe0`
- `0x1140`
- `0x16d0`
- `0x1780`
- `0x1860`
- `0x18b0`
- `0x3d00`
- `0x3f50`
- `0x4070`
- `0x4f20`
- `0x5370`
- `0x53c0`
- `0x53f0`
- `0x5700`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x1550  ldarg.0
0x1551  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Info
0x1556  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x155b  starg.s  0
0x155d  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x1562  ldarg.0
0x1563  ldarg.1
0x1564  callvirt instance void [NLog]NLog.Logger::Info(string, object[])
0x1569  ret
```
