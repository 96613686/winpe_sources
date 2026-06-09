# Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::.ctor

- ea: `0x37c0`
- end: `0x37f7`
- name: `Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::.ctor`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2320`
- `0x4de0`

## pseudocode

```c

```

## disassembly

```asm
0x37c0  ldarg.0
0x37c1  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x37c6  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::cancellationTokenSource
0x37cb  ldarg.0
0x37cc  call     instance void [mscorlib]System.Object::.ctor()
0x37d1  ldarg.0
0x37d2  ldarg.1
0x37d3  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::stopSignal
0x37d8  ldarg.0
0x37d9  ldarg.2
0x37da  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::logger
0x37df  ldarg.0
0x37e0  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::stopSignal
0x37e5  ldarg.0
0x37e6  ldftn    instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::OnStopRequested(object sender, class [mscorlib]System.EventArgs e)
0x37ec  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>::.ctor(object, native int)
0x37f1  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal::add_StopRequested(class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>)
0x37f6  ret
```
