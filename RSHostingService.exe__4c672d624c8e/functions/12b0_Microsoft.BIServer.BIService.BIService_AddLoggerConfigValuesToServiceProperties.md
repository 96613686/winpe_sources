# Microsoft.BIServer.BIService.BIService::AddLoggerConfigValuesToServiceProperties

- ea: `0x12b0`
- end: `0x1320`
- name: `Microsoft.BIServer.BIService.BIService::AddLoggerConfigValuesToServiceProperties`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10e0`
- `0x3390`

## callees

- `0x330`
- `0x360`
- `0x780`
- `0x7a0`
- `0x7e0`
- `0x8a0`
- `0x12b0`

## string_xrefs

- `0x12dd`: `Logger.path`

## pseudocode

```c

```

## disassembly

```asm
0x12b0  call     bool Microsoft.BIServer.RSHostingService.RsTraceConfig::ValidateTraceConfigFileExists()
0x12b5  brfalse.s loc_131F
0x12b7  call     class Microsoft.BIServer.RSHostingService.RsTraceConfig Microsoft.BIServer.RSHostingService.RsTraceConfig::LoadFromFile()
0x12bc  stloc.0
0x12bd  ldarg.1
0x12be  ldstr    aLoggerLevel// "Logger.level"
0x12c3  ldloc.0
0x12c4  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Level()
0x12c9  stloc.1
0x12ca  ldloca.s 1
0x12cc  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level
0x12d2  callvirt instance string [mscorlib]System.Object::ToString()
0x12d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x12dc  ldarg.1
0x12dd  ldstr    aLoggerPath// "Logger.path"
0x12e2  ldloc.0
0x12e3  callvirt instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_LogFolderPath()
0x12e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x12ed  ldarg.1
0x12ee  ldstr    aLoggerRollmb// "Logger.rollMb"
0x12f3  ldloc.0
0x12f4  callvirt instance int32 Microsoft.BIServer.RSHostingService.RsTraceConfig::get_FileSizeLimitMb()
0x12f9  stloc.2
0x12fa  ldloca.s 2
0x12fc  call     instance string [mscorlib]System.Int32::ToString()
0x1301  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1306  ldarg.1
0x1307  ldstr    aLoggerKeepfile// "Logger.keepFilesForDays"
0x130c  ldloc.0
0x130d  callvirt instance int32 Microsoft.BIServer.RSHostingService.RsTraceConfig::get_KeepFilesForDays()
0x1312  stloc.2
0x1313  ldloca.s 2
0x1315  call     instance string [mscorlib]System.Int32::ToString()
0x131a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x131f  ret
```
