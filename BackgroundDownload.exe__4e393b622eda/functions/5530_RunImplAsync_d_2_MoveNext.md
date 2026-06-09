# <RunImplAsync>d__2::MoveNext

- ea: `0x5530`
- end: `0x58f6`
- name: `<RunImplAsync>d__2::MoveNext`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x18f0`
- `0x1900`
- `0x1910`
- `0x1a60`
- `0x1ae0`
- `0x1b10`
- `0x1b70`
- `0x1c30`
- `0x1c50`
- `0x1cd0`
- `0x1cf0`
- `0x2640`
- `0x26a0`
- `0x2950`
- `0x2ed0`
- `0x5530`

## string_xrefs

- `0x5713`: `Another Visual Studio installation is running. You'll need to close it before you continue.`
- `0x56bd`: `Update Check`
- `0x57b9`: `Update check only operation exits with code: {0}`
- `0x5807`: `UpdateChecker cancelled: `
- `0x5845`: `Failed: UpdateChecker Exception`

## pseudocode

```c

```

## disassembly

```asm
0x5530  ldarg.0
0x5531  ldfld    int32 <RunImplAsync>d__2::<>1__state
0x5536  stloc.0
0x5537  ldarg.0
0x5538  ldfld    class Microsoft.VisualStudio.Setup.UpdateChecker <RunImplAsync>d__2::<>4__this
0x553d  stloc.1
0x553e  ldloc.0
0x553f  ldc.i4.2
0x5540  ble.un.s loc_5549
0x5542  ldarg.0
0x5543  ldc.i4.2
0x5544  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__2::<result>5__2
0x5549  nop
0x554a  ldloc.0
0x554b  switch   loc_559A, loc_55FB, loc_56B1
0x555c  ldloc.1
0x555d  ldarg.0
0x555e  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__2::cancellationToken
0x5563  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x5568  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x556d  stloc.3
0x556e  ldloca.s 3
0x5570  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x5575  brtrue.s loc_55B6
0x5577  ldarg.0
0x5578  ldc.i4.0
0x5579  dup
0x557a  stloc.0
0x557b  stfld    int32 <RunImplAsync>d__2::<>1__state
0x5580  ldarg.0
0x5581  ldloc.3
0x5582  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x5587  ldarg.0
0x5588  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x558d  ldloca.s 3
0x558f  ldarg.0
0x5590  call     T0x2B000065
0x5595  leave    loc_58F5
0x559a  ldarg.0
0x559b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x55a0  stloc.3
0x55a1  ldarg.0
0x55a2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x55a7  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x55ad  ldarg.0
0x55ae  ldc.i4.m1
0x55af  dup
0x55b0  stloc.0
0x55b1  stfld    int32 <RunImplAsync>d__2::<>1__state
0x55b6  ldloca.s 3
0x55b8  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x55bd  ldloc.1
0x55be  ldarg.0
0x55bf  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__2::cancellationToken
0x55c4  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CleanupLogsAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x55c9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x55ce  stloc.3
0x55cf  ldloca.s 3
0x55d1  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x55d6  brtrue.s loc_5617
0x55d8  ldarg.0
0x55d9  ldc.i4.1
0x55da  dup
0x55db  stloc.0
0x55dc  stfld    int32 <RunImplAsync>d__2::<>1__state
0x55e1  ldarg.0
0x55e2  ldloc.3
0x55e3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x55e8  ldarg.0
0x55e9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x55ee  ldloca.s 3
0x55f0  ldarg.0
0x55f1  call     T0x2B000065
0x55f6  leave    loc_58F5
0x55fb  ldarg.0
0x55fc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x5601  stloc.3
0x5602  ldarg.0
0x5603  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <RunImplAsync>d__2::<>u__1
0x5608  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x560e  ldarg.0
0x560f  ldc.i4.m1
0x5610  dup
0x5611  stloc.0
0x5612  stfld    int32 <RunImplAsync>d__2::<>1__state
0x5617  ldloca.s 3
0x5619  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x561e  ldarg.0
0x561f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5624  dup
0x5625  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADACTIVITYID
0x562a  ldloc.1
0x562b  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x5630  callvirt instance string Microsoft.VisualStudio.Setup.CommandLine::get_ActivityId()
0x5635  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x563a  dup
0x563b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISCHILD
0x5640  ldloc.1
0x5641  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x5646  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsChildProcess()
0x564b  box      [mscorlib]System.Boolean
0x5650  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5655  dup
0x5656  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISUPDATECHECKONLY
0x565b  ldloc.1
0x565c  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x5661  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsUpdateCheckOnly()
0x5666  box      [mscorlib]System.Boolean
0x566b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5670  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__2::<telemetryProperties>5__3
0x5675  ldloc.1
0x5676  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x567b  dup
0x567c  brtrue.s loc_5681
0x567e  pop
0x567f  br.s     loc_568C
0x5681  ldarg.0
0x5682  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__2::<telemetryProperties>5__3
0x5687  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::SetSharedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x568c  ldarg.0
0x568d  ldloc.1
0x568e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x5693  dup
0x5694  brtrue.s loc_569A
0x5696  pop
0x5697  ldnull
0x5698  br.s     loc_56AC
0x569a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEVENT
0x569f  ldarg.0
0x56a0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__2::<telemetryProperties>5__3
0x56a5  ldc.i4.0
0x56a6  ldc.i4.0
0x56a7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x56ac  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__2::<telemetryOperation>5__4
0x56b1  nop
0x56b2  ldloc.0
0x56b3  ldc.i4.2
0x56b4  beq.s    loc_56CC
0x56b6  ldarg.0
0x56b7  ldloc.1
0x56b8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x56bd  ldstr    aUpdateCheck// "Update Check"
0x56c2  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0x56c7  stfld    class Microsoft.VisualStudio.Setup.OperationLogger <RunImplAsync>d__2::<>7__wrap4
0x56cc  nop
0x56cd  ldloc.0
0x56ce  ldc.i4.2
0x56cf  pop
0x56d0  pop
0x56d1  nop
0x56d2  ldloc.0
0x56d3  ldc.i4.2
0x56d4  beq      loc_576B
0x56d9  ldloc.1
0x56da  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x56df  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsChildProcess()
0x56e4  call     class Microsoft.VisualStudio.Setup.IWork Microsoft.VisualStudio.Setup.WorkFactory::Create(bool isChildProcess)
0x56e9  stloc.s  4
0x56eb  ldloc.1
0x56ec  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService Microsoft.VisualStudio.Setup.UpdateChecker::singletonService
0x56f1  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService::GetSingletonLock()
0x56f6  brtrue.s loc_571E
0x56f8  ldloc.1
0x56f9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x56fe  dup
0x56ff  brtrue.s loc_5704
0x5701  pop
0x5702  br.s     loc_5713
0x5704  ldstr    aFailedToGetSin// "Failed to get singleton lock"
0x5709  call     T0x2B00000A
0x570e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5713  ldstr    aAnotherVisualS// "Another Visual Studio installation is r"...
0x5718  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x571d  throw
0x571e  ldloc.1
0x571f  ldloc.s  4
0x5721  ldloc.1
0x5722  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x5727  callvirt instance string Microsoft.VisualStudio.Setup.CommandLine::get_InstanceId()
0x572c  ldarg.0
0x572d  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__2::cancellationToken
0x5732  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CheckForUpdatesAsync(class Microsoft.VisualStudio.Setup.IWork primaryChild, string instanceId, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x5737  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::GetAwaiter()
0x573c  stloc.s  6
0x573e  ldloca.s 6
0x5740  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::get_IsCompleted()
0x5745  brtrue.s loc_5788
0x5747  ldarg.0
0x5748  ldc.i4.2
0x5749  dup
0x574a  stloc.0
0x574b  stfld    int32 <RunImplAsync>d__2::<>1__state
0x5750  ldarg.0
0x5751  ldloc.s  6
0x5753  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__2::<>u__2
0x5758  ldarg.0
0x5759  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x575e  ldloca.s 6
0x5760  ldarg.0
0x5761  call     T0x2B000066
0x5766  leave    loc_58F5
0x576b  ldarg.0
0x576c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__2::<>u__2
0x5771  stloc.s  6
0x5773  ldarg.0
0x5774  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> <RunImplAsync>d__2::<>u__2
0x5779  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>
0x577f  ldarg.0
0x5780  ldc.i4.m1
0x5781  dup
0x5782  stloc.0
0x5783  stfld    int32 <RunImplAsync>d__2::<>1__state
0x5788  ldloca.s 6
0x578a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult>::GetResult()
0x578f  stloc.s  5
0x5791  ldarg.0
0x5792  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <RunImplAsync>d__2::<telemetryProperties>5__3
0x5797  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADHASUPDATE
0x579c  ldloc.s  5
0x579e  callvirt instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EngineUpdateRequired()
0x57a3  box      [mscorlib]System.Boolean
0x57a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x57ad  ldloc.1
0x57ae  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x57b3  dup
0x57b4  brtrue.s loc_57B9
0x57b6  pop
0x57b7  br.s     loc_57D9
0x57b9  ldstr    aUpdateCheckOnl// "Update check only operation exits with "...
0x57be  ldloc.s  5
0x57c0  callvirt instance int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_UpdateResultCode()
0x57c5  box      [mscorlib]System.Int32
0x57ca  call     string [mscorlib]System.String::Format(string, object)
0x57cf  call     T0x2B00000A
0x57d4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x57d9  ldarg.0
0x57da  ldloc.s  5
0x57dc  callvirt instance int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_UpdateResultCode()
0x57e1  brfalse.s loc_57E6
0x57e3  ldc.i4.5
0x57e4  br.s     loc_57E7
0x57e6  ldc.i4.0
0x57e7  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__2::<result>5__2
0x57ec  ldloc.s  5
0x57ee  callvirt instance int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_UpdateResultCode()
0x57f3  stloc.2
0x57f4  leave    loc_58E1
0x57f9  stloc.s  7
0x57fb  ldloc.1
0x57fc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x5801  dup
0x5802  brtrue.s loc_5807
0x5804  pop
0x5805  br.s     loc_5822
0x5807  ldstr    aUpdatecheckerC// "UpdateChecker cancelled: "
0x580c  ldloc.s  7
0x580e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5813  call     string [mscorlib]System.String::Concat(string, string)
0x5818  call     T0x2B00000A
0x581d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5822  ldarg.0
0x5823  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__2::<telemetryOperation>5__4
0x5828  dup
0x5829  brtrue.s loc_582E
0x582b  pop
0x582c  br.s     loc_583A
0x582e  ldloc.s  7
0x5830  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5835  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordCancel(string)
0x583a  ldarg.0
0x583b  ldc.i4.2
0x583c  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__2::<result>5__2
0x5841  rethrow
0x5843  stloc.s  8
0x5845  ldstr    aFailedUpdatech// "Failed: UpdateChecker Exception"
0x584a  stloc.s  9
0x584c  ldarg.0
0x584d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <RunImplAsync>d__2::<telemetryOperation>5__4
0x5852  dup
0x5853  brtrue.s loc_5858
0x5855  pop
0x5856  br.s     loc_5864
0x5858  ldloc.s  9
0x585a  ldloc.s  8
0x585c  ldloc.s  9
0x585e  ldc.i4.1
0x585f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x5864  ldloc.1
0x5865  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x586a  dup
0x586b  brtrue.s loc_5870
0x586d  pop
0x586e  br.s     loc_587E
0x5870  ldloc.s  8
0x5872  ldloc.s  9
0x5874  call     T0x2B00000A
0x5879  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x587e  ldarg.0
0x587f  ldc.i4.5
0x5880  stfld    valuetype Microsoft.VisualStudio.Setup.OperationResult <RunImplAsync>d__2::<result>5__2
  ... truncated ...
```
