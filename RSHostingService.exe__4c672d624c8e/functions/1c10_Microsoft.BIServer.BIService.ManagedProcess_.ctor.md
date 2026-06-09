# Microsoft.BIServer.BIService.ManagedProcess::.ctor

- ea: `0x1c10`
- end: `0x1c4c`
- name: `Microsoft.BIServer.BIService.ManagedProcess::.ctor`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bf0`
- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x1c10  ldarg.0
0x1c11  call     instance void [mscorlib]System.Object::.ctor()
0x1c16  ldarg.0
0x1c17  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::MaxWaitPeriod
0x1c1c  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::BackOffExpirePeriod
0x1c21  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.ManagedProcess::InitialWaitPeriod
0x1c26  ldsfld   int32 Microsoft.BIServer.BIService.ManagedProcess::BackOffMultiplier
0x1c2b  conv.r8
0x1c2c  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::.ctor(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, float64)
0x1c31  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff Microsoft.BIServer.BIService.ManagedProcess::_exponentialBackoff
0x1c36  ldarg.0
0x1c37  ldarg.1
0x1c38  stfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::_processConfig
0x1c3d  ldarg.0
0x1c3e  ldarg.3
0x1c3f  stfld    bool Microsoft.BIServer.BIService.ManagedProcess::_isManagementProcess
0x1c44  ldarg.0
0x1c45  ldarg.2
0x1c46  stfld    class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher Microsoft.BIServer.BIService.ManagedProcess::_processLauncher
0x1c4b  ret
```
