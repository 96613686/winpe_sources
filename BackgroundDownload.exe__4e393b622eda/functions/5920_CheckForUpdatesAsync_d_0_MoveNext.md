# <CheckForUpdatesAsync>d__0::MoveNext

- ea: `0x5920`
- end: `0x5b5b`
- name: `<CheckForUpdatesAsync>d__0::MoveNext`
- size: `571`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x2600`
- `0x2950`
- `0x5920`

## string_xrefs

- `0x5931`: `services`
- `0x5973`: `Check for updates`
- `0x5a91`: `Need a newer version of setup to read latest catalogs.`
- `0x5ac1`: `Check for update operation has been cancelled.`
- `0x5adc`: `Failed checking for product updates.`

## pseudocode

```c

```

## disassembly

```asm
0x5920  ldarg.0
0x5921  ldfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5926  stloc.0
0x5927  ldloc.0
0x5928  ldc.i4.1
0x5929  ble.un.s loc_5982
0x592b  ldarg.0
0x592c  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5931  ldstr    aServices// "services"
0x5936  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x593b  ldarg.0
0x593c  ldarg.0
0x593d  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5942  ldc.i4.1
0x5943  call     T0x2B000011
0x5948  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x594d  ldarg.0
0x594e  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5953  ldc.i4.1
0x5954  call     T0x2B000003
0x5959  stloc.2
0x595a  ldarg.0
0x595b  ldarg.0
0x595c  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5961  ldc.i4.1
0x5962  call     T0x2B000002
0x5967  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__3
0x596c  ldarg.0
0x596d  ldarg.0
0x596e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5973  ldstr    aCheckForUpdate// "Check for updates"
0x5978  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0x597d  stfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap3
0x5982  nop
0x5983  ldloc.0
0x5984  ldc.i4.1
0x5985  pop
0x5986  pop
0x5987  nop
0x5988  ldloc.0
0x5989  brfalse.s loc_59DF
0x598b  ldloc.0
0x598c  ldc.i4.1
0x598d  beq.s    loc_5A03
0x598f  ldloc.2
0x5990  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetAllInstances()
0x5995  stloc.3
0x5996  ldloc.3
0x5997  brfalse.s loc_5A03
0x5999  ldarg.0
0x599a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__3
0x599f  ldloc.3
0x59a0  ldarg.0
0x59a1  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x59a6  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::EnsureExistingChannelsAreCachedAsync(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>, valuetype [mscorlib]System.Threading.CancellationToken)
0x59ab  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x59b0  stloc.s  4
0x59b2  ldloca.s 4
0x59b4  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x59b9  brtrue.s loc_59FC
0x59bb  ldarg.0
0x59bc  ldc.i4.0
0x59bd  dup
0x59be  stloc.0
0x59bf  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x59c4  ldarg.0
0x59c5  ldloc.s  4
0x59c7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x59cc  ldarg.0
0x59cd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x59d2  ldloca.s 4
0x59d4  ldarg.0
0x59d5  call     T0x2B000067
0x59da  leave    loc_5B5A
0x59df  ldarg.0
0x59e0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x59e5  stloc.s  4
0x59e7  ldarg.0
0x59e8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x59ed  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x59f3  ldarg.0
0x59f4  ldc.i4.m1
0x59f5  dup
0x59f6  stloc.0
0x59f7  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x59fc  ldloca.s 4
0x59fe  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x5a03  nop
0x5a04  ldloc.0
0x5a05  ldc.i4.1
0x5a06  beq.s    loc_5A4D
0x5a08  ldarg.0
0x5a09  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__3
0x5a0e  ldarg.0
0x5a0f  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x5a14  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::UpdateAllAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x5a19  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x5a1e  stloc.s  5
0x5a20  ldloca.s 5
0x5a22  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x5a27  brtrue.s loc_5A6A
0x5a29  ldarg.0
0x5a2a  ldc.i4.1
0x5a2b  dup
0x5a2c  stloc.0
0x5a2d  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5a32  ldarg.0
0x5a33  ldloc.s  5
0x5a35  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CheckForUpdatesAsync>d__0::<>u__2
0x5a3a  ldarg.0
0x5a3b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x5a40  ldloca.s 5
0x5a42  ldarg.0
0x5a43  call     T0x2B000068
0x5a48  leave    loc_5B5A
0x5a4d  ldarg.0
0x5a4e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CheckForUpdatesAsync>d__0::<>u__2
0x5a53  stloc.s  5
0x5a55  ldarg.0
0x5a56  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CheckForUpdatesAsync>d__0::<>u__2
0x5a5b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x5a61  ldarg.0
0x5a62  ldc.i4.m1
0x5a63  dup
0x5a64  stloc.0
0x5a65  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5a6a  ldloca.s 5
0x5a6c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x5a71  pop
0x5a72  leave.s  loc_5AA2
0x5a74  isinst   [mscorlib]System.Exception
0x5a79  dup
0x5a7a  brtrue.s loc_5A80
0x5a7c  pop
0x5a7d  ldc.i4.0
0x5a7e  br.s     loc_5A88
0x5a80  call     T0x2B000069
0x5a85  ldc.i4.0
0x5a86  cgt.un
0x5a88  endfilter
0x5a8a  pop
0x5a8b  ldarg.0
0x5a8c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5a91  ldstr    aNeedANewerVers// "Need a newer version of setup to read l"...
0x5a96  call     T0x2B00000A
0x5a9b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5aa0  leave.s  loc_5AA2
0x5aa2  leave.s  loc_5AED
0x5aa4  isinst   [mscorlib]System.Exception
0x5aa9  dup
0x5aaa  brtrue.s loc_5AB0
0x5aac  pop
0x5aad  ldc.i4.0
0x5aae  br.s     loc_5AB8
0x5ab0  call     T0x2B00006A
0x5ab5  ldc.i4.0
0x5ab6  cgt.un
0x5ab8  endfilter
0x5aba  pop
0x5abb  ldarg.0
0x5abc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5ac1  ldstr    aCheckForUpdate_0// "Check for update operation has been can"...
0x5ac6  call     T0x2B00000A
0x5acb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5ad0  leave.s  loc_5AED
0x5ad2  stloc.s  6
0x5ad4  ldarg.0
0x5ad5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5ada  ldloc.s  6
0x5adc  ldstr    aFailedChecking// "Failed checking for product updates."
0x5ae1  call     T0x2B00000A
0x5ae6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5aeb  leave.s  loc_5AED
0x5aed  ldc.i4.0
0x5aee  ldnull
0x5aef  ldnull
0x5af0  ldc.i4.0
0x5af1  newobj   instance void Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor(bool EngineUpdateRequired, string OpcUrl, class [mscorlib]System.Version OpcVersion, int32 UpdateResultCode)
0x5af6  stloc.1
0x5af7  leave.s  loc_5B38
0x5af9  ldloc.0
0x5afa  ldc.i4.0
0x5afb  bge.s    loc_5B10
0x5afd  ldarg.0
0x5afe  ldfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap3
0x5b03  brfalse.s loc_5B10
0x5b05  ldarg.0
0x5b06  ldfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap3
0x5b0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b10  endfinally
0x5b11  stloc.s  7
0x5b13  ldarg.0
0x5b14  ldc.i4.s 0xFE
0x5b16  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5b1b  ldarg.0
0x5b1c  ldnull
0x5b1d  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5b22  ldarg.0
0x5b23  ldnull
0x5b24  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__3
0x5b29  ldarg.0
0x5b2a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x5b2f  ldloc.s  7
0x5b31  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::SetException(class [mscorlib]System.Exception)
0x5b36  leave.s  loc_5B5A
0x5b38  ldarg.0
0x5b39  ldc.i4.s 0xFE
0x5b3b  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5b40  ldarg.0
0x5b41  ldnull
0x5b42  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5b47  ldarg.0
0x5b48  ldnull
0x5b49  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__3
0x5b4e  ldarg.0
0x5b4f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x5b54  ldloc.1
0x5b55  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::SetResult(var<u1>)
0x5b5a  ret
```
