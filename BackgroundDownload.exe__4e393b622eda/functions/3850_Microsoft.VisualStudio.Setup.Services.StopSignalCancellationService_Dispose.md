# Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::Dispose

- ea: `0x3850`
- end: `0x3885`
- name: `Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::Dispose`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3890`

## callees

- `0x3850`

## pseudocode

```c

```

## disassembly

```asm
0x3850  ldarg.0
0x3851  ldfld    bool Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::isDisposed
0x3856  brtrue.s loc_3884
0x3858  ldarg.1
0x3859  brfalse.s loc_387D
0x385b  ldarg.0
0x385c  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::stopSignal
0x3861  ldarg.0
0x3862  ldftn    instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::OnStopRequested(object sender, class [mscorlib]System.EventArgs e)
0x3868  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>::.ctor(object, native int)
0x386d  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal::remove_StopRequested(class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>)
0x3872  ldarg.0
0x3873  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::cancellationTokenSource
0x3878  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Dispose()
0x387d  ldarg.0
0x387e  ldc.i4.1
0x387f  stfld    bool Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::isDisposed
0x3884  ret
```
