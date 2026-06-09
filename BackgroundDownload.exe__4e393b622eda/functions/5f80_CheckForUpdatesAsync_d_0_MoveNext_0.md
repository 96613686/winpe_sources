# <CheckForUpdatesAsync>d__0::MoveNext_0

- ea: `0x5f80`
- end: `0x62ea`
- name: `<CheckForUpdatesAsync>d__0::MoveNext_0`
- size: `874`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x2600`
- `0x2950`
- `0x2f60`
- `0x2fc0`
- `0x5f80`

## string_xrefs

- `0x5f98`: `services`
- `0x5fff`: `Check for updates`
- `0x61b5`: `Check for update operation has been cancelled.`
- `0x61e3`: `Failed checking for product updates.`
- `0x6249`: `Failed to record update info`

## pseudocode

```c

```

## disassembly

```asm
0x5f80  ldarg.0
0x5f81  ldfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x5f86  stloc.0
0x5f87  ldarg.0
0x5f88  ldfld    class Microsoft.VisualStudio.Setup.WorkPrimaryProcess <CheckForUpdatesAsync>d__0::<>4__this
0x5f8d  stloc.1
0x5f8e  ldloc.0
0x5f8f  ldc.i4.1
0x5f90  ble.un.s loc_600E
0x5f92  ldarg.0
0x5f93  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5f98  ldstr    aServices// "services"
0x5f9d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5fa2  ldarg.0
0x5fa3  ldarg.0
0x5fa4  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5fa9  ldc.i4.1
0x5faa  call     T0x2B000011
0x5faf  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5fb4  ldarg.0
0x5fb5  ldarg.0
0x5fb6  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5fbb  ldc.i4.1
0x5fbc  call     T0x2B000003
0x5fc1  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery <CheckForUpdatesAsync>d__0::<query>5__3
0x5fc6  ldarg.0
0x5fc7  ldarg.0
0x5fc8  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5fcd  ldc.i4.1
0x5fce  call     T0x2B000002
0x5fd3  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x5fd8  ldarg.0
0x5fd9  ldarg.0
0x5fda  ldfld    class [mscorlib]System.IServiceProvider <CheckForUpdatesAsync>d__0::services
0x5fdf  ldc.i4.1
0x5fe0  call     T0x2B000001
0x5fe5  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService <CheckForUpdatesAsync>d__0::<accountProfileService>5__5
0x5fea  ldarg.0
0x5feb  ldc.i4.0
0x5fec  stfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x5ff1  ldarg.0
0x5ff2  ldc.i4.0
0x5ff3  stfld    bool <CheckForUpdatesAsync>d__0::<engineUpdateRequired>5__7
0x5ff8  ldarg.0
0x5ff9  ldarg.0
0x5ffa  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x5fff  ldstr    aCheckForUpdate// "Check for updates"
0x6004  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0x6009  stfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap7
0x600e  nop
0x600f  ldloc.0
0x6010  ldc.i4.1
0x6011  ble.un.s loc_6018
0x6013  ldnull
0x6014  stloc.3
0x6015  ldnull
0x6016  stloc.s  4
0x6018  nop
0x6019  ldloc.0
0x601a  brfalse.s loc_6087
0x601c  ldloc.0
0x601d  ldc.i4.1
0x601e  beq      loc_60AB
0x6023  ldarg.0
0x6024  ldarg.0
0x6025  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery <CheckForUpdatesAsync>d__0::<query>5__3
0x602a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetAllInstances()
0x602f  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <CheckForUpdatesAsync>d__0::<instances>5__9
0x6034  ldarg.0
0x6035  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <CheckForUpdatesAsync>d__0::<instances>5__9
0x603a  brfalse.s loc_60AB
0x603c  ldarg.0
0x603d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x6042  ldarg.0
0x6043  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <CheckForUpdatesAsync>d__0::<instances>5__9
0x6048  ldarg.0
0x6049  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x604e  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::EnsureExistingChannelsAreCachedAsync(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>, valuetype [mscorlib]System.Threading.CancellationToken)
0x6053  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x6058  stloc.s  5
0x605a  ldloca.s 5
0x605c  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6061  brtrue.s loc_60A4
0x6063  ldarg.0
0x6064  ldc.i4.0
0x6065  dup
0x6066  stloc.0
0x6067  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x606c  ldarg.0
0x606d  ldloc.s  5
0x606f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x6074  ldarg.0
0x6075  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x607a  ldloca.s 5
0x607c  ldarg.0
0x607d  call     T0x2B00006F
0x6082  leave    loc_62E9
0x6087  ldarg.0
0x6088  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x608d  stloc.s  5
0x608f  ldarg.0
0x6090  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x6095  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x609b  ldarg.0
0x609c  ldc.i4.m1
0x609d  dup
0x609e  stloc.0
0x609f  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x60a4  ldloca.s 5
0x60a6  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x60ab  nop
0x60ac  ldloc.0
0x60ad  ldc.i4.1
0x60ae  beq.s    loc_6108
0x60b0  ldloc.1
0x60b1  ldarg.0
0x60b2  ldfld    string <CheckForUpdatesAsync>d__0::instanceId
0x60b7  ldarg.0
0x60b8  ldfld    class [System]System.Uri <CheckForUpdatesAsync>d__0::installChannelUri
0x60bd  ldarg.0
0x60be  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <CheckForUpdatesAsync>d__0::<instances>5__9
0x60c3  ldarg.0
0x60c4  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x60c9  ldarg.0
0x60ca  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CheckForUpdatesAsync>d__0::cancellationToken
0x60cf  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.WorkPrimaryProcess::ChannelUpdateCheckAsync(string instanceId, class [System]System.Uri installChannelUri, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> instances, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager channelManager, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x60d4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x60d9  stloc.s  5
0x60db  ldloca.s 5
0x60dd  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x60e2  brtrue.s loc_6125
0x60e4  ldarg.0
0x60e5  ldc.i4.1
0x60e6  dup
0x60e7  stloc.0
0x60e8  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x60ed  ldarg.0
0x60ee  ldloc.s  5
0x60f0  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x60f5  ldarg.0
0x60f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <CheckForUpdatesAsync>d__0::<>t__builder
0x60fb  ldloca.s 5
0x60fd  ldarg.0
0x60fe  call     T0x2B00006F
0x6103  leave    loc_62E9
0x6108  ldarg.0
0x6109  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x610e  stloc.s  5
0x6110  ldarg.0
0x6111  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CheckForUpdatesAsync>d__0::<>u__1
0x6116  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x611c  ldarg.0
0x611d  ldc.i4.m1
0x611e  dup
0x611f  stloc.0
0x6120  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x6125  ldloca.s 5
0x6127  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x612c  leave.s  loc_6158
0x612e  pop
0x612f  ldarg.0
0x6130  ldc.i4.1
0x6131  stfld    bool <CheckForUpdatesAsync>d__0::<engineUpdateRequired>5__7
0x6136  leave.s  loc_6158
0x6138  isinst   [mscorlib]System.AggregateException
0x613d  dup
0x613e  brtrue.s loc_6144
0x6140  pop
0x6141  ldc.i4.0
0x6142  br.s     loc_614C
0x6144  call     T0x2B000069
0x6149  ldc.i4.0
0x614a  cgt.un
0x614c  endfilter
0x614e  pop
0x614f  ldarg.0
0x6150  ldc.i4.1
0x6151  stfld    bool <CheckForUpdatesAsync>d__0::<engineUpdateRequired>5__7
0x6156  leave.s  loc_6158
0x6158  leave.s  loc_6178
0x615a  ldloc.0
0x615b  ldc.i4.0
0x615c  bge.s    loc_6177
0x615e  ldarg.0
0x615f  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x6164  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::get_UpdateEngineUriString()
0x6169  stloc.3
0x616a  ldarg.0
0x616b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x6170  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::get_UpdateClientVersion()
0x6175  stloc.s  4
0x6177  endfinally
0x6178  ldarg.0
0x6179  ldfld    bool <CheckForUpdatesAsync>d__0::<engineUpdateRequired>5__7
0x617e  ldloc.3
0x617f  ldloc.s  4
0x6181  ldarg.0
0x6182  ldfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x6187  newobj   instance void Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor(bool EngineUpdateRequired, string OpcUrl, class [mscorlib]System.Version OpcVersion, int32 UpdateResultCode)
0x618c  stloc.2
0x618d  leave    loc_62B9
0x6192  isinst   [mscorlib]System.Exception
0x6197  dup
0x6198  brtrue.s loc_619E
0x619a  pop
0x619b  ldc.i4.0
0x619c  br.s     loc_61A6
0x619e  call     T0x2B00006A
0x61a3  ldc.i4.0
0x61a4  cgt.un
0x61a6  endfilter
0x61a8  pop
0x61a9  ldarg.0
0x61aa  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x61af  dup
0x61b0  brtrue.s loc_61B5
0x61b2  pop
0x61b3  br.s     loc_61C4
0x61b5  ldstr    aCheckForUpdate_0// "Check for update operation has been can"...
0x61ba  call     T0x2B00000A
0x61bf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x61c4  leave.s  loc_61F4
0x61c6  stloc.s  6
0x61c8  ldarg.0
0x61c9  ldloc.s  6
0x61cb  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x61d0  stfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x61d5  ldarg.0
0x61d6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x61db  dup
0x61dc  brtrue.s loc_61E1
0x61de  pop
0x61df  br.s     loc_61F2
0x61e1  ldloc.s  6
0x61e3  ldstr    aFailedChecking// "Failed checking for product updates."
0x61e8  call     T0x2B00000A
0x61ed  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x61f2  leave.s  loc_61F4
0x61f4  leave.s  loc_625B
0x61f6  ldloc.0
0x61f7  ldc.i4.0
0x61f8  bge.s    loc_625A
0x61fa  ldarg.0
0x61fb  ldfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x6200  brtrue.s loc_625A
0x6202  ldloc.1
0x6203  ldarg.0
0x6204  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery <CheckForUpdatesAsync>d__0::<query>5__3
0x6209  ldarg.0
0x620a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager <CheckForUpdatesAsync>d__0::<channelManager>5__4
0x620f  ldarg.0
0x6210  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService <CheckForUpdatesAsync>d__0::<accountProfileService>5__5
0x6215  ldarg.0
0x6216  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x621b  ldarg.0
0x621c  ldfld    bool <CheckForUpdatesAsync>d__0::<engineUpdateRequired>5__7
0x6221  ldarg.0
0x6222  ldfld    string <CheckForUpdatesAsync>d__0::instanceId
0x6227  call     instance void Microsoft.VisualStudio.Setup.WorkPrimaryProcess::RecordUpdateInformation(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery query, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager channelManager, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IAccountProfileService accountProfileService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, bool engineUpdateRequired, string singleInstanceId)
0x622c  leave.s  loc_625A
0x622e  stloc.s  7
0x6230  ldarg.0
0x6231  ldc.i4   0x64A
0x6236  stfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x623b  ldarg.0
0x623c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <CheckForUpdatesAsync>d__0::<logger>5__2
0x6241  dup
0x6242  brtrue.s loc_6247
0x6244  pop
0x6245  br.s     loc_6258
0x6247  ldloc.s  7
0x6249  ldstr    aFailedToRecord// "Failed to record update info"
0x624e  call     T0x2B00000A
0x6253  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x6258  rethrow
0x625a  endfinally
0x625b  ldc.i4.0
0x625c  ldnull
0x625d  ldnull
0x625e  ldarg.0
0x625f  ldfld    int32 <CheckForUpdatesAsync>d__0::<updateResultCode>5__6
0x6264  newobj   instance void Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor(bool EngineUpdateRequired, string OpcUrl, class [mscorlib]System.Version OpcVersion, int32 UpdateResultCode)
0x6269  stloc.2
0x626a  leave.s  loc_62B9
0x626c  ldloc.0
0x626d  ldc.i4.0
0x626e  bge.s    loc_6283
0x6270  ldarg.0
0x6271  ldfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap7
0x6276  brfalse.s loc_6283
0x6278  ldarg.0
0x6279  ldfld    class Microsoft.VisualStudio.Setup.OperationLogger <CheckForUpdatesAsync>d__0::<>7__wrap7
0x627e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6283  endfinally
0x6284  stloc.s  8
0x6286  ldarg.0
0x6287  ldc.i4.s 0xFE
0x6289  stfld    int32 <CheckForUpdatesAsync>d__0::<>1__state
0x628e  ldarg.0
0x628f  ldnull
  ... truncated ...
```
