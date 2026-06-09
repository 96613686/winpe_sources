# Microsoft.BIServer.HostingEnvironment.Logger::Create_0

- ea: `0xf80`
- end: `0xfd1`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Create_0`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x7c0`
- `0x820`
- `0x870`
- `0xe60`
- `0x1140`

## string_xrefs

- `0xf97`: `Logger.path`

## pseudocode

```c

```

## disassembly

```asm
0xf80  ldarg.0
0xf81  ldarg.1
0xf82  ldstr    aLoggerLevel// "Logger.level"
0xf87  ldstr    aInfo// "Info"
0xf8c  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string key, string defaultValue)
0xf91  call     valuetype Level Microsoft.BIServer.HostingEnvironment.Logger::ParseLevel(string levelString)
0xf96  ldarg.1
0xf97  ldstr    aLoggerPath// "Logger.path"
0xf9c  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string key)
0xfa1  ldarg.1
0xfa2  ldstr    aLoggerRollmb// "Logger.rollMb"
0xfa7  ldc.i4.s 0x20
0xfa9  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xfae  ldarg.1
0xfaf  ldstr    aLoggerKeepfile// "Logger.keepFilesForDays"
0xfb4  ldc.i4.s 0xE
0xfb6  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xfbb  ldarg.1
0xfbc  ldstr    aLoggerAsyncque// "Logger.asyncQueueDepth"
0xfc1  ldc.i4   0x1388
0xfc6  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xfcb  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.Logger::Create(string filePrefix, valuetype Level level, string traceFolder, [opt] int32 rollAtMb, [opt] int32 keepFilesForDays, [opt] int32 asyncQueueLimit)
0xfd0  ret
```
