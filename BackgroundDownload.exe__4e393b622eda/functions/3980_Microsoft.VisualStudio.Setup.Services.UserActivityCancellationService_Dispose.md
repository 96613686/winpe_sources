# Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::Dispose

- ea: `0x3980`
- end: `0x39b5`
- name: `Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::Dispose`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x39c0`

## callees

- `0x2570`
- `0x3980`

## pseudocode

```c

```

## disassembly

```asm
0x3980  ldarg.0
0x3981  ldfld    bool Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::isDisposed
0x3986  brtrue.s loc_39B4
0x3988  ldarg.1
0x3989  brfalse.s loc_39AD
0x398b  ldarg.0
0x398c  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::userActivityMonitor
0x3991  ldarg.0
0x3992  ldftn    instance void Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::OnUserIdleStateChanged(object sender, class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs e)
0x3998  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs>::.ctor(object, native int)
0x399d  callvirt instance void Microsoft.VisualStudio.Setup.IUserActivityMonitor::remove_UserIdleStateChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> value)
0x39a2  ldarg.0
0x39a3  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x39a8  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Dispose()
0x39ad  ldarg.0
0x39ae  ldc.i4.1
0x39af  stfld    bool Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::isDisposed
0x39b4  ret
```
