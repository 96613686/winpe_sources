# <DelayUntilResourcesAvailableAsync>d__28::MoveNext

- ea: `0x16310`
- end: `0x163c1`
- name: `<DelayUntilResourcesAvailableAsync>d__28::MoveNext`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb8c0`
- `0x10200`
- `0x140b0`
- `0x16310`

## pseudocode

```c

```

## disassembly

```asm
0x16310  ldarg.0
0x16311  ldfld    int32 <DelayUntilResourcesAvailableAsync>d__28::<>1__state
0x16316  stloc.0
0x16317  ldloc.0
0x16318  brfalse.s loc_16371
0x1631a  call     class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x1631f  brfalse.s loc_16394
0x16321  call     class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x16326  callvirt instance class Microsoft.ReportingServices.ProcessingRenderingCommon.IResourceTicket Microsoft.ReportingServices.Diagnostics.RequestContextBase::get_ResourceTicket()
0x1632b  brfalse.s loc_16394
0x1632d  call     class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x16332  callvirt instance class Microsoft.ReportingServices.ProcessingRenderingCommon.IResourceTicket Microsoft.ReportingServices.Diagnostics.RequestContextBase::get_ResourceTicket()
0x16337  ldarg.0
0x16338  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DelayUntilResourcesAvailableAsync>d__28::cancellationToken
0x1633d  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.ReportingServices.ProcessingRenderingCommon.IResourceTicket::DelayUntilResourcesAvailableAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x16342  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x16347  stloc.1
0x16348  ldloca.s 1
0x1634a  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x1634f  brtrue.s loc_1638D
0x16351  ldarg.0
0x16352  ldc.i4.0
0x16353  dup
0x16354  stloc.0
0x16355  stfld    int32 <DelayUntilResourcesAvailableAsync>d__28::<>1__state
0x1635a  ldarg.0
0x1635b  ldloc.1
0x1635c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DelayUntilResourcesAvailableAsync>d__28::<>u__1
0x16361  ldarg.0
0x16362  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DelayUntilResourcesAvailableAsync>d__28::<>t__builder
0x16367  ldloca.s 1
0x16369  ldarg.0
0x1636a  call     T0x2B000013
0x1636f  leave.s  loc_163C0
0x16371  ldarg.0
0x16372  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DelayUntilResourcesAvailableAsync>d__28::<>u__1
0x16377  stloc.1
0x16378  ldarg.0
0x16379  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DelayUntilResourcesAvailableAsync>d__28::<>u__1
0x1637e  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x16384  ldarg.0
0x16385  ldc.i4.m1
0x16386  dup
0x16387  stloc.0
0x16388  stfld    int32 <DelayUntilResourcesAvailableAsync>d__28::<>1__state
0x1638d  ldloca.s 1
0x1638f  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x16394  leave.s  loc_163AD
0x16396  stloc.2
0x16397  ldarg.0
0x16398  ldc.i4.s 0xFE
0x1639a  stfld    int32 <DelayUntilResourcesAvailableAsync>d__28::<>1__state
0x1639f  ldarg.0
0x163a0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DelayUntilResourcesAvailableAsync>d__28::<>t__builder
0x163a5  ldloc.2
0x163a6  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x163ab  leave.s  loc_163C0
0x163ad  ldarg.0
0x163ae  ldc.i4.s 0xFE
0x163b0  stfld    int32 <DelayUntilResourcesAvailableAsync>d__28::<>1__state
0x163b5  ldarg.0
0x163b6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DelayUntilResourcesAvailableAsync>d__28::<>t__builder
0x163bb  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x163c0  ret
```
