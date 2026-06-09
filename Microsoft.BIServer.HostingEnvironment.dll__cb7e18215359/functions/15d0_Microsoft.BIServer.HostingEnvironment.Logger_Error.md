# Microsoft.BIServer.HostingEnvironment.Logger::Error

- ea: `0x15d0`
- end: `0x15ea`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Error`
- size: `26`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb90`
- `0x1860`
- `0x18b0`
- `0x23f0`
- `0x2960`
- `0x2a20`
- `0x3070`
- `0x5a70`
- `0x6510`
- `0x6a80`
- `0x6c10`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  ldarg.0
0x15d1  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Error
0x15d6  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x15db  starg.s  0
0x15dd  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x15e2  ldarg.0
0x15e3  ldarg.1
0x15e4  callvirt instance void [NLog]NLog.Logger::Error(string, object[])
0x15e9  ret
```
