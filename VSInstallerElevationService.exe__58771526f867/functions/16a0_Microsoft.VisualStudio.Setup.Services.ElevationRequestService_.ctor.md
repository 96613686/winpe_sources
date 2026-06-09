# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::.ctor

- ea: `0x16a0`
- end: `0x16d4`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::.ctor`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1c30`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldarg.0
0x16a1  call     instance void [mscorlib]System.Object::.ctor()
0x16a6  ldarg.0
0x16a7  ldarg.1
0x16a8  stfld    string Microsoft.VisualStudio.Setup.Services.ElevationRequestService::installerServicePath
0x16ad  ldarg.0
0x16ae  ldarg.2
0x16af  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.ElevationRequestService::fileSystem
0x16b4  ldarg.0
0x16b5  ldarg.3
0x16b6  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Services.ElevationRequestService::signatureVerifier
0x16bb  ldarg.0
0x16bc  ldarg.s  4
0x16be  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.ElevationRequestService::processService
0x16c3  ldarg.0
0x16c4  ldarg.s  5
0x16c6  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.ElevationRequestService::telemetry
0x16cb  ldarg.0
0x16cc  ldarg.s  6
0x16ce  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x16d3  ret
```
