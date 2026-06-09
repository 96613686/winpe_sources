# Microsoft.VisualStudio.Setup.ElevationServiceManager::.ctor

- ea: `0xc50`
- end: `0xc8f`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::.ctor`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0xc50  ldarg.0
0xc51  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0xc56  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.ElevationServiceManager::cancellationToken
0xc5b  ldarg.0
0xc5c  call     instance void [mscorlib]System.Object::.ctor()
0xc61  ldarg.0
0xc62  ldarg.1
0xc63  stfld    class Microsoft.VisualStudio.Setup.Services.IPipeFactory Microsoft.VisualStudio.Setup.ElevationServiceManager::pipeFactory
0xc68  ldarg.0
0xc69  ldarg.2
0xc6a  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.ElevationServiceManager::registry
0xc6f  ldarg.0
0xc70  ldarg.3
0xc71  stfld    class Microsoft.VisualStudio.Setup.Services.IStreamJsonRpcFactory Microsoft.VisualStudio.Setup.ElevationServiceManager::rpcFactory
0xc76  ldarg.0
0xc77  ldarg.s  4
0xc79  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.IRpcConnectionValidator Microsoft.VisualStudio.Setup.ElevationServiceManager::clientValidator
0xc7e  ldarg.0
0xc7f  ldarg.s  5
0xc81  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ElevationServiceManager::telemetry
0xc86  ldarg.0
0xc87  ldarg.s  6
0xc89  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xc8e  ret
```
