# Microsoft.VisualStudio.Setup.CleanLayoutOperation::Run

- ea: `0x5830`
- end: `0x5a68`
- name: `Microsoft.VisualStudio.Setup.CleanLayoutOperation::Run`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5830`
- `0x15c20`
- `0x15c90`
- `0x15cf0`
- `0x15d10`
- `0x15d30`
- `0x15e30`
- `0x163d0`
- `0x19c90`
- `0x19cd0`
- `0x27720`
- `0x29280`
- `0x3a6a0`
- `0x5a220`
- `0x5b5e0`

## string_xrefs

- `0x587d`: `CleanLayoutNoFilesToDelete`
- `0x58da`: `No directory to clean up.`
- `0x590f`: `These files are going to be deleted from the layout directory:`
- `0x59a1`: `CleanLayoutConfirmToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x5830  ldarga.s 1
0x5832  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x5837  ldarg.0
0x5838  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::Initialize()
0x583d  ldarg.0
0x583e  call     instance bool Microsoft.VisualStudio.Setup.LayoutOperationBase::Plan()
0x5843  brtrue.s loc_5846
0x5845  ret
0x5846  ldarg.0
0x5847  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x584c  brfalse.s loc_585E
0x584e  ldarg.0
0x584f  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5854  call     T0x2B000015
0x5859  brtrue   loc_58EA
0x585e  ldloca.s 3
0x5860  initobj  [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message
0x5866  ldloca.s 3
0x5868  ldc.i4.1
0x5869  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Type
0x586e  ldloca.s 3
0x5870  ldc.i4.7
0x5871  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType>::.ctor(var<u1>)
0x5876  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Activity
0x587b  ldloca.s 3
0x587d  ldstr    aCleanlayoutnof// "CleanLayoutNoFilesToDelete"
0x5882  ldnull
0x5883  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x5888  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::NeutralString
0x588d  ldloca.s 3
0x588f  call     string Microsoft.VisualStudio.Setup.Resources::get_CleanLayoutNoFilesToDelete()
0x5894  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::LocalizedString
0x5899  ldloc.3
0x589a  stloc.2
0x589b  ldarg.0
0x589c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.LayoutOperationBase::get_MessageBus()
0x58a1  ldloc.2
0x58a2  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus::NotifyMessageAsync(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message)
0x58a7  ldarg.1
0x58a8  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait(valuetype [mscorlib]System.Threading.CancellationToken)
0x58ad  ldarg.0
0x58ae  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CLEANLAYOUTOTALPACKAGECOUNTPPROPERTY
0x58b3  ldc.i4.0
0x58b4  box      [mscorlib]System.Int32
0x58b9  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x58be  ldarg.0
0x58bf  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CLEANLAYOUTFAILEDPACKAGECOUNTPPROPERTY
0x58c4  ldc.i4.0
0x58c5  box      [mscorlib]System.Int32
0x58ca  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x58cf  ldarg.0
0x58d0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x58d5  dup
0x58d6  brtrue.s loc_58DA
0x58d8  pop
0x58d9  ret
0x58da  ldstr    aNoDirectoryToC// "No directory to clean up."
0x58df  call     T0x2B000003
0x58e4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x58e9  ret
0x58ea  ldarg.0
0x58eb  call     instance class Microsoft.VisualStudio.Setup.Services.ProgressAggregator Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Progress()
0x58f0  ldarg.0
0x58f1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Activities.CleanPackage> Microsoft.VisualStudio.Setup.CleanLayoutOperation::cleanPackages
0x58f6  ldarg.0
0x58f7  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Services()
0x58fc  ldnull
0x58fd  ldc.i4.m1
0x58fe  callvirt instance void Microsoft.VisualStudio.Setup.Services.ProgressAggregatorBase::Initialize(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackageProgress> packageProgressCollection, [opt] class [mscorlib]System.IServiceProvider services, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance instance, [opt] valuetype Microsoft.VisualStudio.Setup.ProgressType type)
0x5903  ldarg.0
0x5904  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x5909  dup
0x590a  brtrue.s loc_590F
0x590c  pop
0x590d  br.s     loc_591E
0x590f  ldstr    aTheseFilesAreG// "These files are going to be deleted fro"...
0x5914  call     T0x2B000003
0x5919  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x591e  ldarg.0
0x591f  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5924  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x5929  stloc.s  4
0x592b  br.s     loc_594E
0x592d  ldloc.s  4
0x592f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x5934  stloc.s  5
0x5936  ldarg.0
0x5937  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x593c  dup
0x593d  brtrue.s loc_5942
0x593f  pop
0x5940  br.s     loc_594E
0x5942  ldloc.s  5
0x5944  call     T0x2B000003
0x5949  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x594e  ldloc.s  4
0x5950  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5955  brtrue.s loc_592D
0x5957  leave.s  loc_5965
0x5959  ldloc.s  4
0x595b  brfalse.s loc_5964
0x595d  ldloc.s  4
0x595f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5964  endfinally
0x5965  ldloca.s 3
0x5967  initobj  [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message
0x596d  ldloca.s 3
0x596f  ldc.i4.2
0x5970  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Type
0x5975  ldloca.s 3
0x5977  ldc.i4.7
0x5978  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType>::.ctor(var<u1>)
0x597d  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.ActivityType> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Activity
0x5982  ldloca.s 3
0x5984  ldc.i4.3
0x5985  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResultTypes [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::AcceptsResultTypes
0x598a  ldloca.s 3
0x598c  ldc.i4.1
0x598d  stfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResultTypes [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::DefaultResultType
0x5992  ldloca.s 3
0x5994  ldarg.0
0x5995  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x599a  stfld    object [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::Context
0x599f  ldloca.s 3
0x59a1  ldstr    aCleanlayoutcon// "CleanLayoutConfirmToDelete"
0x59a6  ldnull
0x59a7  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetNeutralResourceString(string resourceId, [opt] class [mscorlib]System.Resources.ResourceManager resourceManager)
0x59ac  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::NeutralString
0x59b1  ldloca.s 3
0x59b3  call     string Microsoft.VisualStudio.Setup.Resources::get_CleanLayoutConfirmToDelete()
0x59b8  stfld    string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message::LocalizedString
0x59bd  ldloc.3
0x59be  stloc.0
0x59bf  ldarg.0
0x59c0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.LayoutOperationBase::get_MessageBus()
0x59c5  ldloca.s 0
0x59c7  ldarg.1
0x59c8  call     valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResult Microsoft.VisualStudio.Setup.Message.Extensions::Prompt(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus bus, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.Message& message, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x59cd  stloc.1
0x59ce  ldloca.s 1
0x59d0  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResultTypes [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Message.MessageResult::get_Type()
0x59d5  ldc.i4.1
0x59d6  bne.un.s loc_5A4D
0x59d8  ldarg.0
0x59d9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x59de  dup
0x59df  brtrue.s loc_59E4
0x59e1  pop
0x59e2  br.s     loc_59F3
0x59e4  ldstr    aUserAcceptedDe// "User accepted deletion of directories."
0x59e9  call     T0x2B000003
0x59ee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x59f3  ldarg.0
0x59f4  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.CleanLayoutOperation::parallelCleans
0x59f9  ldarg.1
0x59fa  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Coordinator::Run(valuetype [mscorlib]System.Threading.CancellationToken token)
0x59ff  ldarg.0
0x5a00  ldfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.CleanLayoutOperation::parallelCleans
0x5a05  callvirt instance void Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator::Wait()
0x5a0a  leave.s  loc_5A0F
0x5a0c  pop
0x5a0d  leave.s  loc_5A0F
0x5a0f  ldarg.0
0x5a10  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CLEANLAYOUTOTALPACKAGECOUNTPPROPERTY
0x5a15  ldarg.0
0x5a16  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryToBeCleaned
0x5a1b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x5a20  box      [mscorlib]System.Int32
0x5a25  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x5a2a  ldarg.0
0x5a2b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CLEANLAYOUTFAILEDPACKAGECOUNTPPROPERTY
0x5a30  ldarg.0
0x5a31  ldfld    class [System]System.Collections.Concurrent.ConcurrentBag`1<string> Microsoft.VisualStudio.Setup.CleanLayoutOperation::directoryFailedToBeCleaned
0x5a36  dup
0x5a37  brtrue.s loc_5A3D
0x5a39  pop
0x5a3a  ldc.i4.0
0x5a3b  br.s     loc_5A42
0x5a3d  call     instance int32 class [System]System.Collections.Concurrent.ConcurrentBag`1<string>::get_Count()
0x5a42  box      [mscorlib]System.Int32
0x5a47  call     instance void Microsoft.VisualStudio.Setup.LayoutOperationBase::AddTelemetryProperty(string propertyName, object propertyValue)
0x5a4c  ret
0x5a4d  ldarg.0
0x5a4e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.LayoutOperationBase::get_Logger()
0x5a53  dup
0x5a54  brtrue.s loc_5A58
0x5a56  pop
0x5a57  ret
0x5a58  ldstr    aUserDeclinedDe// "User declined deletion of directories."
0x5a5d  call     T0x2B000003
0x5a62  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a67  ret
```
