# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::.ctor

- ea: `0x3690`
- end: `0x36d6`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::.ctor`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4de0`

## callees

- `0x2560`
- `0x2580`

## pseudocode

```c

```

## disassembly

```asm
0x3690  ldarg.0
0x3691  call     instance void [mscorlib]System.Object::.ctor()
0x3696  ldarg.0
0x3697  ldarg.1
0x3698  stfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::idleDownloadManager
0x369d  ldarg.0
0x369e  ldarg.2
0x369f  stfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::activeDownloadManager
0x36a4  ldarg.0
0x36a5  ldarg.3
0x36a6  stfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::userActivityMonitor
0x36ab  ldarg.0
0x36ac  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::userActivityMonitor
0x36b1  ldarg.0
0x36b2  ldftn    instance void Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::OnUserIdleStateChanged(object sender, class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs e)
0x36b8  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs>::.ctor(object, native int)
0x36bd  callvirt instance void Microsoft.VisualStudio.Setup.IUserActivityMonitor::add_UserIdleStateChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> value)
0x36c2  ldarg.0
0x36c3  ldarg.0
0x36c4  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::userActivityMonitor
0x36c9  callvirt instance bool Microsoft.VisualStudio.Setup.IUserActivityMonitor::get_IsIdle()
0x36ce  volatile.
0x36d0  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::isIdle
0x36d5  ret
```
