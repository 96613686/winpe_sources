# Microsoft.BIServer.BIService.BIService::.cctor

- ea: `0x1430`
- end: `0x14f3`
- name: `Microsoft.BIServer.BIService.BIService::.cctor`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x14a1`: `ServiceWatchdogIntervalInSeconds`
- `0x14b7`: `ReadConfigStartDelay`
- `0x14cd`: `ReadConfigMaxDelay`

## pseudocode

```c

```

## disassembly

```asm
0x1430  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x1435  ldstr    aWebapimaxwaitm// "WebApiMaxWaitMS"
0x143a  ldc.i4   0x3E8
0x143f  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x1444  conv.r8
0x1445  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x144a  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffMaxWait
0x144f  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x1454  ldstr    aWebapibackoffe// "WebApiBackOffExpireSeconds"
0x1459  ldc.i4.s 0x3C
0x145b  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x1460  conv.r8
0x1461  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1466  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffExpire
0x146b  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x1470  ldstr    aWebapiinitialw// "WebApiInitialWaitMS"
0x1475  ldc.i4.s 0xA
0x1477  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x147c  conv.r8
0x147d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x1482  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffInitialWait
0x1487  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x148c  ldstr    aWebapibackoffm// "WebApiBackoffMultiplier"
0x1491  ldc.i4.2
0x1492  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x1497  stsfld   int32 Microsoft.BIServer.BIService.BIService::WebApiBackoffMultiplier
0x149c  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x14a1  ldstr    aServicewatchdo// "ServiceWatchdogIntervalInSeconds"
0x14a6  ldc.i4.s 0xA
0x14a8  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x14ad  stsfld   int32 Microsoft.BIServer.BIService.BIService::ServiceWatchdogIntervalInSeconds
0x14b2  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x14b7  ldstr    aReadconfigstar// "ReadConfigStartDelay"
0x14bc  ldc.i4.s 0x1E
0x14be  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x14c3  stsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigStartDelay
0x14c8  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x14cd  ldstr    aReadconfigmaxd// "ReadConfigMaxDelay"
0x14d2  ldc.i4   0x3C0
0x14d7  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x14dc  stsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigMaxDelay
0x14e1  ldc.i4.0
0x14e2  stsfld   int32 Microsoft.BIServer.BIService.BIService::ReadConfigAttemptCount
0x14e7  ldc.i4.0
0x14e8  newarr   [mscorlib]System.String
0x14ed  stsfld   string[] Microsoft.BIServer.BIService.BIService::NoArgs
0x14f2  ret
```
