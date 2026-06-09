# Microsoft.BIServer.HostingEnvironment.Logger::Error_0

- ea: `0x15f0`
- end: `0x160b`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Error_0`
- size: `27`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19c0`
- `0x2870`
- `0x35f0`
- `0x3da0`
- `0x3e40`
- `0x3f50`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.1
0x15f1  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Error
0x15f6  call     string Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext(string formatString, class [NLog]NLog.LogLevel level)
0x15fb  starg.s  1
0x15fd  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x1602  ldarg.0
0x1603  ldarg.1
0x1604  ldarg.2
0x1605  callvirt instance void [NLog]NLog.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x160a  ret
```
