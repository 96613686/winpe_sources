# Microsoft.BIServer.BIService.Program::CreateLogger

- ea: `0x2430`
- end: `0x246f`
- name: `Microsoft.BIServer.BIService.Program::CreateLogger`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x23e0`

## callees

- `0x330`
- `0x360`
- `0x780`
- `0x7a0`
- `0x7e0`
- `0x8a0`
- `0x2430`

## string_xrefs

- `0x2430`: `RSHostingService`

## pseudocode

```c

```

## disassembly

```asm
0x2430  ldstr    aRshostingservi// "RSHostingService"
0x2435  stloc.0
0x2436  call     bool Microsoft.BIServer.RSHostingService.RsTraceConfig::ValidateTraceConfigFileExists()
0x243b  brtrue.s loc_2445
0x243d  ldloc.0
0x243e  ldc.i4.4
0x243f  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Create(string, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level)
0x2444  ret
0x2445  call     class Microsoft.BIServer.RSHostingService.RsTraceConfig Microsoft.BIServer.RSHostingService.RsTraceConfig::LoadFromFile()
0x244a  stloc.1
0x244b  ldloc.0
0x244c  ldloc.1
0x244d  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Level()
0x2452  ldloc.1
0x2453  callvirt instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_LogFolderPath()
0x2458  ldloc.1
0x2459  callvirt instance int32 Microsoft.BIServer.RSHostingService.RsTraceConfig::get_FileSizeLimitMb()
0x245e  ldloc.1
0x245f  callvirt instance int32 Microsoft.BIServer.RSHostingService.RsTraceConfig::get_KeepFilesForDays()
0x2464  ldc.i4   0x1388
0x2469  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Create(string, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger/Level, string, int32, int32, int32)
0x246e  ret
```
