# <SingleDeleteRetry>d__7::MoveNext

- ea: `0x6e80`
- end: `0x6f5e`
- name: `<SingleDeleteRetry>d__7::MoveNext`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x6e80`

## string_xrefs

- `0x6ef0`: `Retry: Deleting scoped temp file : {0}`
- `0x6f16`: `Retry: Failed to delete temp file {0}. Abandoning...`

## pseudocode

```c

```

## disassembly

```asm
0x6e80  ldarg.0
0x6e81  ldfld    int32 <SingleDeleteRetry>d__7::<>1__state
0x6e86  stloc.0
0x6e87  ldarg.0
0x6e88  ldfld    class Microsoft.BIServer.Configuration.ScopedFileDelete <SingleDeleteRetry>d__7::<>4__this
0x6e8d  stloc.1
0x6e8e  ldloc.0
0x6e8f  brfalse.s loc_6ECD
0x6e91  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.ScopedFileDelete::DeleteRetrySpan
0x6e96  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(valuetype [mscorlib]System.TimeSpan)
0x6e9b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x6ea0  stloc.2
0x6ea1  ldloca.s 2
0x6ea3  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6ea8  brtrue.s loc_6EE9
0x6eaa  ldarg.0
0x6eab  ldc.i4.0
0x6eac  dup
0x6ead  stloc.0
0x6eae  stfld    int32 <SingleDeleteRetry>d__7::<>1__state
0x6eb3  ldarg.0
0x6eb4  ldloc.2
0x6eb5  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SingleDeleteRetry>d__7::<>u__1
0x6eba  ldarg.0
0x6ebb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SingleDeleteRetry>d__7::<>t__builder
0x6ec0  ldloca.s 2
0x6ec2  ldarg.0
0x6ec3  call     T0x2B000041
0x6ec8  leave    loc_6F5D
0x6ecd  ldarg.0
0x6ece  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SingleDeleteRetry>d__7::<>u__1
0x6ed3  stloc.2
0x6ed4  ldarg.0
0x6ed5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SingleDeleteRetry>d__7::<>u__1
0x6eda  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x6ee0  ldarg.0
0x6ee1  ldc.i4.m1
0x6ee2  dup
0x6ee3  stloc.0
0x6ee4  stfld    int32 <SingleDeleteRetry>d__7::<>1__state
0x6ee9  ldloca.s 2
0x6eeb  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x6ef0  ldstr    aRetryDeletingS// "Retry: Deleting scoped temp file : {0}"
0x6ef5  ldc.i4.1
0x6ef6  newarr   [mscorlib]System.Object
0x6efb  dup
0x6efc  ldc.i4.0
0x6efd  ldloc.1
0x6efe  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6f03  stelem.ref
0x6f04  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x6f09  ldloc.1
0x6f0a  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6f0f  call     void [mscorlib]System.IO.File::Delete(string)
0x6f14  leave.s  loc_6F31
0x6f16  ldstr    aRetryFailedToD// "Retry: Failed to delete temp file {0}. "...
0x6f1b  ldc.i4.1
0x6f1c  newarr   [mscorlib]System.Object
0x6f21  dup
0x6f22  ldc.i4.0
0x6f23  ldloc.1
0x6f24  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6f29  stelem.ref
0x6f2a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x6f2f  leave.s  loc_6F31
0x6f31  leave.s  loc_6F4A
0x6f33  stloc.3
0x6f34  ldarg.0
0x6f35  ldc.i4.s 0xFE
0x6f37  stfld    int32 <SingleDeleteRetry>d__7::<>1__state
0x6f3c  ldarg.0
0x6f3d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SingleDeleteRetry>d__7::<>t__builder
0x6f42  ldloc.3
0x6f43  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x6f48  leave.s  loc_6F5D
0x6f4a  ldarg.0
0x6f4b  ldc.i4.s 0xFE
0x6f4d  stfld    int32 <SingleDeleteRetry>d__7::<>1__state
0x6f52  ldarg.0
0x6f53  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SingleDeleteRetry>d__7::<>t__builder
0x6f58  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x6f5d  ret
```
