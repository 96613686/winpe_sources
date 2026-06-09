# Microsoft.BIServer.BIService.ManagedProcess::.cctor

- ea: `0x2030`
- end: `0x209a`
- name: `Microsoft.BIServer.BIService.ManagedProcess::.cctor`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2030  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x2035  ldstr    aMaxwaitminutes// "MaxWaitMinutes"
0x203a  ldc.i4.s 0x3C
0x203c  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x2041  conv.r8
0x2042  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x2047  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::MaxWaitPeriod
0x204c  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x2051  ldstr    aBackoffexpirem// "BackOffExpireMinutes"
0x2056  ldc.i4.s 0x3C
0x2058  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x205d  conv.r8
0x205e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x2063  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::BackOffExpirePeriod
0x2068  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x206d  ldstr    aInitialwaitsec// "InitialWaitSeconds"
0x2072  ldc.i4.s 0x1E
0x2074  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x2079  conv.r8
0x207a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x207f  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::InitialWaitPeriod
0x2084  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x2089  ldstr    aBackoffmultipl// "BackOffMultiplier"
0x208e  ldc.i4.2
0x208f  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x2094  stsfld   int32 Microsoft.BIServer.BIService.ManagedProcess::BackOffMultiplier
0x2099  ret
```
