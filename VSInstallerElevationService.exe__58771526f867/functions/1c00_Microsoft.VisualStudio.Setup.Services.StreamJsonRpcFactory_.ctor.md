# Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::.ctor

- ea: `0x1c00`
- end: `0x1c2c`
- name: `Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  ldarg.0
0x1c01  call     instance void [mscorlib]System.Object::.ctor()
0x1c06  ldarg.0
0x1c07  ldarg.1
0x1c08  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::fileSystem
0x1c0d  ldarg.0
0x1c0e  ldarg.2
0x1c0f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::signatureVerifier
0x1c14  ldarg.0
0x1c15  ldarg.3
0x1c16  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::processService
0x1c1b  ldarg.0
0x1c1c  ldarg.s  4
0x1c1e  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::telemetry
0x1c23  ldarg.0
0x1c24  ldarg.s  5
0x1c26  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::logger
0x1c2b  ret
```
