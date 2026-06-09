# <WriteAsync>d__14::MoveNext

- ea: `0xd420`
- end: `0xd4e0`
- name: `<WriteAsync>d__14::MoveNext`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x47a0`
- `0x5270`
- `0xd420`

## pseudocode

```c

```

## disassembly

```asm
0xd420  ldarg.0
0xd421  ldfld    int32 <WriteAsync>d__14::<>1__state
0xd426  stloc.0
0xd427  ldarg.0
0xd428  ldfld    class System.Net.Http.Handlers.ProgressStream <WriteAsync>d__14::<>4__this
0xd42d  stloc.1
0xd42e  ldloc.0
0xd42f  brfalse.s loc_D483
0xd431  ldloc.1
0xd432  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0xd437  ldarg.0
0xd438  ldfld    unsigned int8[] <WriteAsync>d__14::buffer
0xd43d  ldarg.0
0xd43e  ldfld    int32 <WriteAsync>d__14::offset
0xd443  ldarg.0
0xd444  ldfld    int32 <WriteAsync>d__14::count
0xd449  ldarg.0
0xd44a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <WriteAsync>d__14::cancellationToken
0xd44f  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.IO.Stream::WriteAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xd454  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xd459  stloc.2
0xd45a  ldloca.s 2
0xd45c  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xd461  brtrue.s loc_D49F
0xd463  ldarg.0
0xd464  ldc.i4.0
0xd465  dup
0xd466  stloc.0
0xd467  stfld    int32 <WriteAsync>d__14::<>1__state
0xd46c  ldarg.0
0xd46d  ldloc.2
0xd46e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteAsync>d__14::<>u__1
0xd473  ldarg.0
0xd474  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteAsync>d__14::<>t__builder
0xd479  ldloca.s 2
0xd47b  ldarg.0
0xd47c  call     T0x2B00007A
0xd481  leave.s  loc_D4DF
0xd483  ldarg.0
0xd484  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteAsync>d__14::<>u__1
0xd489  stloc.2
0xd48a  ldarg.0
0xd48b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteAsync>d__14::<>u__1
0xd490  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xd496  ldarg.0
0xd497  ldc.i4.m1
0xd498  dup
0xd499  stloc.0
0xd49a  stfld    int32 <WriteAsync>d__14::<>1__state
0xd49f  ldloca.s 2
0xd4a1  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xd4a6  ldloc.1
0xd4a7  ldarg.0
0xd4a8  ldfld    int32 <WriteAsync>d__14::count
0xd4ad  ldnull
0xd4ae  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesSent(int32 bytesSent, object userState)
0xd4b3  leave.s  loc_D4CC
0xd4b5  stloc.3
0xd4b6  ldarg.0
0xd4b7  ldc.i4.s 0xFE
0xd4b9  stfld    int32 <WriteAsync>d__14::<>1__state
0xd4be  ldarg.0
0xd4bf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteAsync>d__14::<>t__builder
0xd4c4  ldloc.3
0xd4c5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xd4ca  leave.s  loc_D4DF
0xd4cc  ldarg.0
0xd4cd  ldc.i4.s 0xFE
0xd4cf  stfld    int32 <WriteAsync>d__14::<>1__state
0xd4d4  ldarg.0
0xd4d5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteAsync>d__14::<>t__builder
0xd4da  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xd4df  ret
```
