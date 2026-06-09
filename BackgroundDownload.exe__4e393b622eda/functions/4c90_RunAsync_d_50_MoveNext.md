# <RunAsync>d__50::MoveNext

- ea: `0x4c90`
- end: `0x4dbb`
- name: `<RunAsync>d__50::MoveNext`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18f0`
- `0x1910`
- `0x1a30`
- `0x1c50`
- `0x4c90`

## pseudocode

```c

```

## disassembly

```asm
0x4c90  ldarg.0
0x4c91  ldfld    int32 <RunAsync>d__50::<>1__state
0x4c96  stloc.0
0x4c97  ldarg.0
0x4c98  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <RunAsync>d__50::<>4__this
0x4c9d  stloc.1
0x4c9e  ldloc.0
0x4c9f  pop
0x4ca0  nop
0x4ca1  ldloc.0
0x4ca2  brfalse.s loc_4CE2
0x4ca4  ldloc.1
0x4ca5  ldarg.0
0x4ca6  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RunAsync>d__50::cancellationToken
0x4cab  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::RunImplAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x4cb0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x4cb5  stloc.3
0x4cb6  ldloca.s 3
0x4cb8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x4cbd  brtrue.s loc_4CFE
0x4cbf  ldarg.0
0x4cc0  ldc.i4.0
0x4cc1  dup
0x4cc2  stloc.0
0x4cc3  stfld    int32 <RunAsync>d__50::<>1__state
0x4cc8  ldarg.0
0x4cc9  ldloc.3
0x4cca  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <RunAsync>d__50::<>u__1
0x4ccf  ldarg.0
0x4cd0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunAsync>d__50::<>t__builder
0x4cd5  ldloca.s 3
0x4cd7  ldarg.0
0x4cd8  call     T0x2B000059
0x4cdd  leave    loc_4DBA
0x4ce2  ldarg.0
0x4ce3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <RunAsync>d__50::<>u__1
0x4ce8  stloc.3
0x4ce9  ldarg.0
0x4cea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <RunAsync>d__50::<>u__1
0x4cef  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x4cf5  ldarg.0
0x4cf6  ldc.i4.m1
0x4cf7  dup
0x4cf8  stloc.0
0x4cf9  stfld    int32 <RunAsync>d__50::<>1__state
0x4cfe  ldloca.s 3
0x4d00  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x4d05  stloc.2
0x4d06  leave    loc_4DA6
0x4d0b  isinst   [mscorlib]System.Exception
0x4d10  dup
0x4d11  brtrue.s loc_4D17
0x4d13  pop
0x4d14  ldc.i4.0
0x4d15  br.s     loc_4D28
0x4d17  stloc.s  4
0x4d19  ldloc.1
0x4d1a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x4d1f  ldnull
0x4d20  ceq
0x4d22  ldc.i4.0
0x4d23  ceq
0x4d25  ldc.i4.0
0x4d26  cgt.un
0x4d28  endfilter
0x4d2a  pop
0x4d2b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x4d30  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADISUPDATECHECKONLY
0x4d35  stloc.s  6
0x4d37  dup
0x4d38  ldloc.s  6
0x4d3a  ldloc.1
0x4d3b  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x4d40  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsUpdateCheckOnly()
0x4d45  box      [mscorlib]System.Boolean
0x4d4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4d4f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADEXITERRORCODE
0x4d54  stloc.s  7
0x4d56  dup
0x4d57  ldloc.s  7
0x4d59  ldloc.s  4
0x4d5b  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x4d60  box      [mscorlib]System.Int32
0x4d65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4d6a  stloc.s  5
0x4d6c  ldloc.1
0x4d6d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Telemetry()
0x4d72  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::BACKGROUNDDOWNLOADUNHANDLEDEXCEPTIONTHROWNEVENT
0x4d77  ldstr    aBackgrounddown_3// "BackgroundDownload unexpected error"
0x4d7c  ldloc.s  5
0x4d7e  ldloc.s  4
0x4d80  ldnull
0x4d81  ldc.i4.0
0x4d82  ldnull
0x4d83  ldc.i4.0
0x4d84  ldnull
0x4d85  ldc.i4.0
0x4d86  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x4d8b  rethrow
0x4d8d  stloc.s  8
0x4d8f  ldarg.0
0x4d90  ldc.i4.s 0xFE
0x4d92  stfld    int32 <RunAsync>d__50::<>1__state
0x4d97  ldarg.0
0x4d98  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunAsync>d__50::<>t__builder
0x4d9d  ldloc.s  8
0x4d9f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x4da4  leave.s  loc_4DBA
0x4da6  ldarg.0
0x4da7  ldc.i4.s 0xFE
0x4da9  stfld    int32 <RunAsync>d__50::<>1__state
0x4dae  ldarg.0
0x4daf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunAsync>d__50::<>t__builder
0x4db4  ldloc.2
0x4db5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x4dba  ret
```
