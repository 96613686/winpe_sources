# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Dispose

- ea: `0x3730`
- end: `0x375a`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Dispose`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3760`

## callees

- `0x2570`
- `0x3730`

## pseudocode

```c

```

## disassembly

```asm
0x3730  ldarg.0
0x3731  ldfld    bool Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::isDisposed
0x3736  brtrue.s loc_3759
0x3738  ldarg.1
0x3739  brfalse.s loc_3752
0x373b  ldarg.0
0x373c  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::userActivityMonitor
0x3741  ldarg.0
0x3742  ldftn    instance void Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::OnUserIdleStateChanged(object sender, class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs e)
0x3748  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs>::.ctor(object, native int)
0x374d  callvirt instance void Microsoft.VisualStudio.Setup.IUserActivityMonitor::remove_UserIdleStateChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> value)
0x3752  ldarg.0
0x3753  ldc.i4.1
0x3754  stfld    bool Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::isDisposed
0x3759  ret
```
