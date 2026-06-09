# <ReadAsync>d__9::MoveNext

- ea: `0xd330`
- end: `0xd3f4`
- name: `<ReadAsync>d__9::MoveNext`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x4850`
- `0x5270`
- `0xd330`

## pseudocode

```c

```

## disassembly

```asm
0xd330  ldarg.0
0xd331  ldfld    int32 <ReadAsync>d__9::<>1__state
0xd336  stloc.0
0xd337  ldarg.0
0xd338  ldfld    class System.Net.Http.Handlers.ProgressStream <ReadAsync>d__9::<>4__this
0xd33d  stloc.1
0xd33e  ldloc.0
0xd33f  brfalse.s loc_D395
0xd341  ldloc.1
0xd342  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0xd347  ldarg.0
0xd348  ldfld    unsigned int8[] <ReadAsync>d__9::buffer
0xd34d  ldarg.0
0xd34e  ldfld    int32 <ReadAsync>d__9::offset
0xd353  ldarg.0
0xd354  ldfld    int32 <ReadAsync>d__9::count
0xd359  ldarg.0
0xd35a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ReadAsync>d__9::cancellationToken
0xd35f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [mscorlib]System.IO.Stream::ReadAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xd364  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0xd369  stloc.s  4
0xd36b  ldloca.s 4
0xd36d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0xd372  brtrue.s loc_D3B2
0xd374  ldarg.0
0xd375  ldc.i4.0
0xd376  dup
0xd377  stloc.0
0xd378  stfld    int32 <ReadAsync>d__9::<>1__state
0xd37d  ldarg.0
0xd37e  ldloc.s  4
0xd380  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsync>d__9::<>u__1
0xd385  ldarg.0
0xd386  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ReadAsync>d__9::<>t__builder
0xd38b  ldloca.s 4
0xd38d  ldarg.0
0xd38e  call     T0x2B000079
0xd393  leave.s  loc_D3F3
0xd395  ldarg.0
0xd396  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsync>d__9::<>u__1
0xd39b  stloc.s  4
0xd39d  ldarg.0
0xd39e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ReadAsync>d__9::<>u__1
0xd3a3  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0xd3a9  ldarg.0
0xd3aa  ldc.i4.m1
0xd3ab  dup
0xd3ac  stloc.0
0xd3ad  stfld    int32 <ReadAsync>d__9::<>1__state
0xd3b2  ldloca.s 4
0xd3b4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0xd3b9  stloc.3
0xd3ba  ldloc.1
0xd3bb  ldloc.3
0xd3bc  ldnull
0xd3bd  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesReceived(int32 bytesReceived, object userState)
0xd3c2  ldloc.3
0xd3c3  stloc.2
0xd3c4  leave.s  loc_D3DF
0xd3c6  stloc.s  5
0xd3c8  ldarg.0
0xd3c9  ldc.i4.s 0xFE
0xd3cb  stfld    int32 <ReadAsync>d__9::<>1__state
0xd3d0  ldarg.0
0xd3d1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ReadAsync>d__9::<>t__builder
0xd3d6  ldloc.s  5
0xd3d8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0xd3dd  leave.s  loc_D3F3
0xd3df  ldarg.0
0xd3e0  ldc.i4.s 0xFE
0xd3e2  stfld    int32 <ReadAsync>d__9::<>1__state
0xd3e7  ldarg.0
0xd3e8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ReadAsync>d__9::<>t__builder
0xd3ed  ldloc.2
0xd3ee  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0xd3f3  ret
```
