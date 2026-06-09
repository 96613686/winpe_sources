# Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::CreateRpcService

- ea: `0x1c30`
- end: `0x1c93`
- name: `Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::CreateRpcService`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xfb0`
- `0x16a0`
- `0x1b70`
- `0x1ca0`

## pseudocode

```c

```

## disassembly

```asm
0x1c30  ldarg.1
0x1c31  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.IPipe::get_Stream()
0x1c36  ldarg.1
0x1c37  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.IPipe::get_Stream()
0x1c3c  ldnull
0x1c3d  newobj   instance void [StreamJsonRpc]StreamJsonRpc.JsonRpc::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.IO.Stream, object)
0x1c42  dup
0x1c43  ldc.i4.1
0x1c44  callvirt instance void [StreamJsonRpc]StreamJsonRpc.JsonRpc::set_CancelLocallyInvokedMethodsWhenConnectionIsClosed(bool)
0x1c49  newobj   instance void [StreamJsonRpc]StreamJsonRpc.JsonRpcTargetOptions::.ctor()
0x1c4e  dup
0x1c4f  ldc.i4.0
0x1c50  callvirt instance void [StreamJsonRpc]StreamJsonRpc.JsonRpcTargetOptions::set_AllowNonPublicInvocation(bool)
0x1c55  stloc.0
0x1c56  dup
0x1c57  ldarg.0
0x1c58  ldarg.1
0x1c59  call     instance string Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::GetInstallerServicePath(class Microsoft.VisualStudio.Setup.IPipe pipe)
0x1c5e  ldarg.0
0x1c5f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::fileSystem
0x1c64  ldarg.0
0x1c65  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::signatureVerifier
0x1c6a  ldarg.0
0x1c6b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::processService
0x1c70  ldarg.0
0x1c71  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::telemetry
0x1c76  ldarg.0
0x1c77  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::logger
0x1c7c  newobj   instance void Microsoft.VisualStudio.Setup.Services.ElevationRequestService::.ctor(string installerServicePath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager signatureVerifier, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService processService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x1c81  ldloc.0
0x1c82  callvirt T0x2B00001A
0x1c87  dup
0x1c88  callvirt instance void [StreamJsonRpc]StreamJsonRpc.JsonRpc::StartListening()
0x1c8d  newobj   instance void Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::.ctor(class [StreamJsonRpc]StreamJsonRpc.JsonRpc rpc)
0x1c92  ret
```
