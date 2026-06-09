# Microsoft.BIServer.HostingEnvironment.Logger::Debug_0

- ea: `0x1490`
- end: `0x14ab`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Debug_0`
- size: `27`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3380`
- `0x5bd0`
- `0x5de0`
- `0x5f20`
- `0x6070`
- `0x61c0`
- `0x63d0`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldarg.1
0x1491  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Debug
0x1496  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x149b  starg.s  1
0x149d  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x14a2  ldarg.0
0x14a3  ldarg.1
0x14a4  ldarg.2
0x14a5  callvirt instance void [NLog]NLog.Logger::Debug(class [mscorlib]System.Exception, string, object[])
0x14aa  ret
```
