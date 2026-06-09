# <AddBackgroundDownloadServicesAsync>d__3::MoveNext

- ea: `0x4de0`
- end: `0x506d`
- name: `<AddBackgroundDownloadServicesAsync>d__3::MoveNext`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x1c70`
- `0x1c90`
- `0x23e0`
- `0x2420`
- `0x2440`
- `0x2480`
- `0x3580`
- `0x3690`
- `0x37c0`
- `0x38b0`
- `0x4de0`

## pseudocode

```c

```

## disassembly

```asm
0x4de0  ldarg.0
0x4de1  ldfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x4de6  stloc.0
0x4de7  ldloc.0
0x4de8  brfalse  loc_4E8B
0x4ded  ldarg.0
0x4dee  ldarg.0
0x4def  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4df4  ldc.i4.0
0x4df5  call     T0x2B000011
0x4dfa  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x4dff  ldarg.0
0x4e00  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4e05  ldstr    aGlobalVssetupb// "Global\\VsSetupBackgroundDownloader"
0x4e0a  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.NullStopSignal::.ctor()
0x4e0f  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.MutexService::.ctor()
0x4e14  ldarg.0
0x4e15  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x4e1a  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.SingletonService::.ctor(string, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IMutexService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x4e1f  ldc.i4.0
0x4e20  ldc.i4.0
0x4e21  callvirt T0x2B00002C
0x4e26  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressReporter::.ctor()
0x4e2b  stloc.1
0x4e2c  ldarg.0
0x4e2d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4e32  ldloc.1
0x4e33  ldc.i4.0
0x4e34  ldc.i4.0
0x4e35  callvirt T0x2B00005A
0x4e3a  ldarg.0
0x4e3b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4e40  ldloc.1
0x4e41  ldc.i4.0
0x4e42  ldc.i4.0
0x4e43  callvirt T0x2B00005B
0x4e48  ldarg.0
0x4e49  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4e4e  ldc.i4.1
0x4e4f  call     T0x2B000054
0x4e54  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.CompositionRoot::GetHybridExperimentFlagAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService remoteSettings)
0x4e59  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x4e5e  stloc.3
0x4e5f  ldloca.s 3
0x4e61  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x4e66  brtrue.s loc_4EA7
0x4e68  ldarg.0
0x4e69  ldc.i4.0
0x4e6a  dup
0x4e6b  stloc.0
0x4e6c  stfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x4e71  ldarg.0
0x4e72  ldloc.3
0x4e73  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <AddBackgroundDownloadServicesAsync>d__3::<>u__1
0x4e78  ldarg.0
0x4e79  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x4e7e  ldloca.s 3
0x4e80  ldarg.0
0x4e81  call     T0x2B00005C
0x4e86  leave    loc_506C
0x4e8b  ldarg.0
0x4e8c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <AddBackgroundDownloadServicesAsync>d__3::<>u__1
0x4e91  stloc.3
0x4e92  ldarg.0
0x4e93  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <AddBackgroundDownloadServicesAsync>d__3::<>u__1
0x4e98  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x4e9e  ldarg.0
0x4e9f  ldc.i4.m1
0x4ea0  dup
0x4ea1  stloc.0
0x4ea2  stfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x4ea7  ldloca.s 3
0x4ea9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x4eae  brfalse  loc_4F51
0x4eb3  ldarg.0
0x4eb4  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4eb9  ldc.i4.0
0x4eba  call     T0x2B000012
0x4ebf  dup
0x4ec0  brtrue.s loc_4EC5
0x4ec2  pop
0x4ec3  br.s     loc_4ED5
0x4ec5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADHYBRIDDOWNLOAD
0x4eca  ldc.i4.1
0x4ecb  box      [mscorlib]System.Boolean
0x4ed0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::SetSharedProperty(string, object)
0x4ed5  ldarg.0
0x4ed6  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4edb  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManager::.ctor(class [mscorlib]System.IServiceProvider)
0x4ee0  stloc.s  4
0x4ee2  ldarg.0
0x4ee3  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4ee8  ldarg.0
0x4ee9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4eee  ldc.i4.1
0x4eef  call     class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadEngine[] Microsoft.VisualStudio.Setup.CompositionRoot::CreateBITSDownloadEngines(class [mscorlib]System.IServiceProvider services, valuetype [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.Bits.BG_JOB_PRIORITY priority)
0x4ef4  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManager::.ctor(class [mscorlib]System.IServiceProvider, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadEngine>)
0x4ef9  stloc.s  5
0x4efb  ldarg.0
0x4efc  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f01  ldarg.0
0x4f02  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f07  ldloc.s  4
0x4f09  ldloc.s  5
0x4f0b  ldarg.0
0x4f0c  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f11  ldc.i4.1
0x4f12  call     T0x2B00005D
0x4f17  newobj   instance void Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::.ctor(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager idleDownloadManager, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager activeDownloadManager, class Microsoft.VisualStudio.Setup.IUserActivityMonitor userActivityMonitor)
0x4f1c  call     class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManagerAuthenticationProxy Microsoft.VisualStudio.Setup.CompositionRoot::CreateAuthenticationProxy(class [mscorlib]System.IServiceProvider services, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager downloadManager)
0x4f21  ldc.i4.0
0x4f22  ldc.i4.0
0x4f23  callvirt T0x2B00002B
0x4f28  ldarg.0
0x4f29  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f2e  ldarg.0
0x4f2f  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f34  ldc.i4.1
0x4f35  call     T0x2B00002E
0x4f3a  ldarg.0
0x4f3b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x4f40  newobj   instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal stopSignal, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x4f45  ldc.i4.0
0x4f46  ldc.i4.0
0x4f47  callvirt T0x2B00002F
0x4f4c  br       loc_4FDF
0x4f51  ldarg.0
0x4f52  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f57  ldarg.0
0x4f58  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f5d  ldc.i4.1
0x4f5e  ldc.i4.1
0x4f5f  ldc.i4.0
0x4f60  conv.i
0x4f61  call     class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManagerFactory::Create(class [mscorlib]System.IServiceProvider, bool, bool, native int)
0x4f66  ldc.i4.0
0x4f67  ldc.i4.0
0x4f68  callvirt T0x2B00002B
0x4f6d  ldarg.0
0x4f6e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4f73  ldc.i4.1
0x4f74  call     T0x2B00002E
0x4f79  ldarg.0
0x4f7a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x4f7f  newobj   instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal stopSignal, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x4f84  stloc.s  6
0x4f86  ldarg.0
0x4f87  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <AddBackgroundDownloadServicesAsync>d__3::commandLine
0x4f8c  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_CanCancel()
0x4f91  brfalse.s loc_4FD0
0x4f93  call     bool [mscorlib]System.Diagnostics.Debugger::get_IsAttached()
0x4f98  brtrue.s loc_4FD0
0x4f9a  ldarg.0
0x4f9b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4fa0  ldc.i4.1
0x4fa1  call     T0x2B00005D
0x4fa6  ldarg.0
0x4fa7  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4fac  ldc.i4.0
0x4fad  call     T0x2B000011
0x4fb2  newobj   instance void Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::.ctor(class Microsoft.VisualStudio.Setup.IUserActivityMonitor userActivityMonitor, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x4fb7  stloc.s  7
0x4fb9  ldc.i4.2
0x4fba  newarr   Microsoft.VisualStudio.Setup.Services.ICancellationService
0x4fbf  dup
0x4fc0  ldc.i4.0
0x4fc1  ldloc.s  6
0x4fc3  stelem.ref
0x4fc4  dup
0x4fc5  ldc.i4.1
0x4fc6  ldloc.s  7
0x4fc8  stelem.ref
0x4fc9  newobj   instance void Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::.ctor(class Microsoft.VisualStudio.Setup.Services.ICancellationService[] cancellationServices)
0x4fce  stloc.s  6
0x4fd0  ldarg.0
0x4fd1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4fd6  ldloc.s  6
0x4fd8  ldc.i4.0
0x4fd9  ldc.i4.0
0x4fda  callvirt T0x2B00002F
0x4fdf  ldarg.0
0x4fe0  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <AddBackgroundDownloadServicesAsync>d__3::commandLine
0x4fe5  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CommandLine::get_ChildClientVersion()
0x4fea  dup
0x4feb  brtrue.s loc_4FFA
0x4fed  pop
0x4fee  ldarg.0
0x4fef  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x4ff4  ldnull
0x4ff5  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Client::GetClientPackageVersion(class [mscorlib]System.IServiceProvider, string)
0x4ffa  stloc.2
0x4ffb  ldarg.0
0x4ffc  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x5001  ldarg.0
0x5002  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x5007  ldloc.2
0x5008  brtrue.s loc_500D
0x500a  ldnull
0x500b  br.s     loc_5013
0x500d  ldloc.2
0x500e  callvirt instance string [mscorlib]System.Object::ToString()
0x5013  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManager::.ctor(class [mscorlib]System.IServiceProvider, string)
0x5018  ldc.i4.0
0x5019  ldc.i4.0
0x501a  callvirt T0x2B00002D
0x501f  ldarg.0
0x5020  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x5025  ldarg.0
0x5026  ldfld    class Microsoft.VisualStudio.Setup.CommandLine <AddBackgroundDownloadServicesAsync>d__3::commandLine
0x502b  call     void Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadJob(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x5030  leave.s  loc_5052
0x5032  stloc.s  8
0x5034  ldarg.0
0x5035  ldc.i4.s 0xFE
0x5037  stfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x503c  ldarg.0
0x503d  ldnull
0x503e  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x5043  ldarg.0
0x5044  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x5049  ldloc.s  8
0x504b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x5050  leave.s  loc_506C
0x5052  ldarg.0
0x5053  ldc.i4.s 0xFE
0x5055  stfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x505a  ldarg.0
0x505b  ldnull
0x505c  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <AddBackgroundDownloadServicesAsync>d__3::<logger>5__2
0x5061  ldarg.0
0x5062  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x5067  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x506c  ret
```
