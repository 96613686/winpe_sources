# Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::.ctor

- ea: `0x38b0`
- end: `0x391f`
- name: `Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::.ctor`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4de0`

## callees

- `0x2560`
- `0x2580`
- `0x38b0`

## pseudocode

```c

```

## disassembly

```asm
0x38b0  ldarg.0
0x38b1  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x38b6  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x38bb  ldarg.0
0x38bc  call     instance void [mscorlib]System.Object::.ctor()
0x38c1  ldarg.0
0x38c2  ldarg.1
0x38c3  stfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::userActivityMonitor
0x38c8  ldarg.0
0x38c9  ldarg.2
0x38ca  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::logger
0x38cf  ldarg.0
0x38d0  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::userActivityMonitor
0x38d5  ldarg.0
0x38d6  ldftn    instance void Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::OnUserIdleStateChanged(object sender, class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs e)
0x38dc  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs>::.ctor(object, native int)
0x38e1  callvirt instance void Microsoft.VisualStudio.Setup.IUserActivityMonitor::add_UserIdleStateChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs> value)
0x38e6  ldarg.0
0x38e7  ldfld    class Microsoft.VisualStudio.Setup.IUserActivityMonitor Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::userActivityMonitor
0x38ec  callvirt instance bool Microsoft.VisualStudio.Setup.IUserActivityMonitor::get_IsIdle()
0x38f1  brtrue.s loc_391E
0x38f3  ldarg.0
0x38f4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::logger
0x38f9  dup
0x38fa  brtrue.s loc_38FF
0x38fc  pop
0x38fd  br.s     loc_390E
0x38ff  ldstr    aUserIsActiveAt// "User is active at initialization. Cance"...
0x3904  call     T0x2B00000A
0x3909  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x390e  ldarg.0
0x390f  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x3914  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x3919  leave.s  loc_391E
0x391b  pop
0x391c  leave.s  loc_391E
0x391e  ret
```
