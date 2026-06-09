# <InitializeAsync>d__54::MoveNext

- ea: `0x4630`
- end: `0x4831`
- name: `<InitializeAsync>d__54::MoveNext`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18c0`
- `0x18f0`
- `0x1900`
- `0x1910`
- `0x1920`
- `0x1930`
- `0x19b0`
- `0x19c0`
- `0x19d0`
- `0x1aa0`
- `0x1c50`
- `0x4630`

## pseudocode

```c

```

## disassembly

```asm
0x4630  ldarg.0
0x4631  ldfld    int32 <InitializeAsync>d__54::<>1__state
0x4636  stloc.0
0x4637  ldarg.0
0x4638  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <InitializeAsync>d__54::<>4__this
0x463d  stloc.1
0x463e  ldloc.0
0x463f  brfalse.s loc_4661
0x4641  ldloc.1
0x4642  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsDisposed()
0x4647  brfalse.s loc_4654
0x4649  ldstr    aBackgrounddown_0// "BackgroundDownloader"
0x464e  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x4653  throw
0x4654  ldloc.1
0x4655  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsInitialized()
0x465a  brfalse.s loc_4661
0x465c  leave    loc_481D
0x4661  nop
0x4662  ldloc.0
0x4663  brfalse.s loc_46A3
0x4665  ldloc.1
0x4666  ldarg.0
0x4667  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeAsync>d__54::cancellationToken
0x466c  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeRemoteSettingsAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x4671  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x4676  stloc.3
0x4677  ldloca.s 3
0x4679  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x467e  brtrue.s loc_46BF
0x4680  ldarg.0
0x4681  ldc.i4.0
0x4682  dup
0x4683  stloc.0
0x4684  stfld    int32 <InitializeAsync>d__54::<>1__state
0x4689  ldarg.0
0x468a  ldloc.3
0x468b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__54::<>u__1
0x4690  ldarg.0
0x4691  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x4696  ldloca.s 3
0x4698  ldarg.0
0x4699  call     T0x2B000052
0x469e  leave    loc_4830
0x46a3  ldarg.0
0x46a4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__54::<>u__1
0x46a9  stloc.3
0x46aa  ldarg.0
0x46ab  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__54::<>u__1
0x46b0  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x46b6  ldarg.0
0x46b7  ldc.i4.m1
0x46b8  dup
0x46b9  stloc.0
0x46ba  stfld    int32 <InitializeAsync>d__54::<>1__state
0x46bf  ldloca.s 3
0x46c1  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x46c6  leave    loc_478C
0x46cb  stloc.s  4
0x46cd  ldloc.s  4
0x46cf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x46d4  stloc.s  5
0x46d6  ldloc.s  4
0x46d8  call     class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class [mscorlib]System.Exception> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::TryGetWrappedExceptions(class [mscorlib]System.Exception)
0x46dd  dup
0x46de  brtrue.s loc_46E4
0x46e0  pop
0x46e1  ldnull
0x46e2  br.s     loc_4708
0x46e4  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Exception, string> <>c::<>9__54_0
0x46e9  dup
0x46ea  brtrue.s loc_4703
0x46ec  pop
0x46ed  ldsfld   class <>c <>c::<>9
0x46f2  ldftn    instance string <>c::<InitializeAsync>b__54_0(class [mscorlib]System.Exception x)
0x46f8  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Exception, string>::.ctor(object, native int)
0x46fd  dup
0x46fe  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Exception, string> <>c::<>9__54_0
0x4703  call     T0x2B000053
0x4708  stloc.s  6
0x470a  ldloc.s  6
0x470c  brfalse.s loc_471C
0x470e  call     string [mscorlib]System.Environment::get_NewLine()
0x4713  ldloc.s  6
0x4715  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x471a  stloc.s  5
0x471c  ldstr    aCannotGetRemot// "Cannot get remote settings, use default"...
0x4721  ldloc.s  5
0x4723  call     string [mscorlib]System.String::Concat(string, string)
0x4728  stloc.s  7
0x472a  ldloc.1
0x472b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x4730  dup
0x4731  brtrue.s loc_4736
0x4733  pop
0x4734  br.s     loc_4742
0x4736  ldloc.s  7
0x4738  call     T0x2B00000A
0x473d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4742  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x4747  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISUPDATECHECKONLY
0x474c  stloc.s  9
0x474e  dup
0x474f  ldloc.s  9
0x4751  ldloc.1
0x4752  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x4757  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsUpdateCheckOnly()
0x475c  box      [mscorlib]System.Boolean
0x4761  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4766  stloc.s  8
0x4768  ldloc.1
0x4769  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x476e  dup
0x476f  brtrue.s loc_4774
0x4771  pop
0x4772  br.s     loc_478A
0x4774  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADUNHANDLEDEXCEPTIONTHROWNEVENT
0x4779  ldloc.s  7
0x477b  ldloc.s  8
0x477d  ldloc.s  4
0x477f  ldnull
0x4780  ldc.i4.0
0x4781  ldnull
0x4782  ldc.i4.0
0x4783  ldnull
0x4784  ldc.i4.0
0x4785  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x478a  leave.s  loc_478C
0x478c  ldloc.1
0x478d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x4792  isinst   [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger
0x4797  stloc.2
0x4798  ldloc.2
0x4799  brfalse.s loc_47CD
0x479b  ldloc.2
0x479c  ldloc.1
0x479d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x47a2  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::RetryOpenIfFaulted(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry)
0x47a7  pop
0x47a8  ldloc.1
0x47a9  ldloc.2
0x47aa  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::get_Path()
0x47af  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_LogFilePath(string value)
0x47b4  ldloc.1
0x47b5  ldloc.2
0x47b6  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::get_BasePath()
0x47bb  ldloc.2
0x47bc  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::get_BaseName()
0x47c1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x47c6  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_LogFilePrefix(string value)
0x47cb  br.s     loc_47FB
0x47cd  ldloc.1
0x47ce  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePath()
0x47d3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x47d8  brtrue.s loc_47FB
0x47da  ldloc.1
0x47db  ldloc.1
0x47dc  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePath()
0x47e1  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x47e6  ldloc.1
0x47e7  call     instance string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_LogFilePath()
0x47ec  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x47f1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x47f6  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_LogFilePrefix(string value)
0x47fb  ldloc.1
0x47fc  ldc.i4.1
0x47fd  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_IsInitialized(bool value)
0x4802  leave.s  loc_481D
0x4804  stloc.s  0xA
0x4806  ldarg.0
0x4807  ldc.i4.s 0xFE
0x4809  stfld    int32 <InitializeAsync>d__54::<>1__state
0x480e  ldarg.0
0x480f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x4814  ldloc.s  0xA
0x4816  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x481b  leave.s  loc_4830
0x481d  ldarg.0
0x481e  ldc.i4.s 0xFE
0x4820  stfld    int32 <InitializeAsync>d__54::<>1__state
0x4825  ldarg.0
0x4826  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x482b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x4830  ret
```
