# Microsoft.BIServer.HostingEnvironment.Logger::Create

- ea: `0xf10`
- end: `0xf7d`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Create`
- size: `109`
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

- `0xf37`: `Logger.path`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldarg.0
0xf11  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xf16  ldstr    aLoggerLevel// "Logger.level"
0xf1b  ldarga.s 1
0xf1d  constrained. Level
0xf23  callvirt instance string [mscorlib]System.Object::ToString()
0xf28  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string key, string defaultValue)
0xf2d  call     valuetype Level Microsoft.BIServer.HostingEnvironment.Logger::ParseLevel(string levelString)
0xf32  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xf37  ldstr    aLoggerPath// "Logger.path"
0xf3c  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string key)
0xf41  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xf46  ldstr    aLoggerRollmb// "Logger.rollMb"
0xf4b  ldc.i4.s 0x20
0xf4d  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xf52  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xf57  ldstr    aLoggerKeepfile// "Logger.keepFilesForDays"
0xf5c  ldc.i4.s 0xE
0xf5e  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xf63  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0xf68  ldstr    aLoggerAsyncque// "Logger.asyncQueueDepth"
0xf6d  ldc.i4   0x1388
0xf72  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0xf77  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.Logger::Create(string filePrefix, valuetype Level level, string traceFolder, [opt] int32 rollAtMb, [opt] int32 keepFilesForDays, [opt] int32 asyncQueueLimit)
0xf7c  ret
```
