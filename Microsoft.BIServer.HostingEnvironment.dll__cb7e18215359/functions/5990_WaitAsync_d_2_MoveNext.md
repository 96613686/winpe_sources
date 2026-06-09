# <WaitAsync>d__2::MoveNext

- ea: `0x5990`
- end: `0x5a41`
- name: `<WaitAsync>d__2::MoveNext`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x5990`

## pseudocode

```c

```

## disassembly

```asm
0x5990  ldarg.0
0x5991  ldfld    int32 <WaitAsync>d__2::<>1__state
0x5996  stloc.0
0x5997  ldloc.0
0x5998  brfalse.s loc_59DF
0x599a  ldarg.0
0x599b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x59a0  stfld    valuetype [mscorlib]System.DateTime <WaitAsync>d__2::<start>5__2
0x59a5  ldarg.0
0x59a6  ldfld    valuetype [mscorlib]System.TimeSpan <WaitAsync>d__2::timeSpan
0x59ab  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Delay(valuetype [mscorlib]System.TimeSpan)
0x59b0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x59b5  stloc.2
0x59b6  ldloca.s 2
0x59b8  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x59bd  brtrue.s loc_59FB
0x59bf  ldarg.0
0x59c0  ldc.i4.0
0x59c1  dup
0x59c2  stloc.0
0x59c3  stfld    int32 <WaitAsync>d__2::<>1__state
0x59c8  ldarg.0
0x59c9  ldloc.2
0x59ca  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitAsync>d__2::<>u__1
0x59cf  ldarg.0
0x59d0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [mscorlib]System.TimeSpan> <WaitAsync>d__2::<>t__builder
0x59d5  ldloca.s 2
0x59d7  ldarg.0
0x59d8  call     T0x2B000039
0x59dd  leave.s  loc_5A40
0x59df  ldarg.0
0x59e0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitAsync>d__2::<>u__1
0x59e5  stloc.2
0x59e6  ldarg.0
0x59e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitAsync>d__2::<>u__1
0x59ec  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x59f2  ldarg.0
0x59f3  ldc.i4.m1
0x59f4  dup
0x59f5  stloc.0
0x59f6  stfld    int32 <WaitAsync>d__2::<>1__state
0x59fb  ldloca.s 2
0x59fd  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x5a02  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5a07  ldarg.0
0x5a08  ldfld    valuetype [mscorlib]System.DateTime <WaitAsync>d__2::<start>5__2
0x5a0d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5a12  stloc.1
0x5a13  leave.s  loc_5A2C
0x5a15  stloc.3
0x5a16  ldarg.0
0x5a17  ldc.i4.s 0xFE
0x5a19  stfld    int32 <WaitAsync>d__2::<>1__state
0x5a1e  ldarg.0
0x5a1f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [mscorlib]System.TimeSpan> <WaitAsync>d__2::<>t__builder
0x5a24  ldloc.3
0x5a25  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [mscorlib]System.TimeSpan>::SetException(class [mscorlib]System.Exception)
0x5a2a  leave.s  loc_5A40
0x5a2c  ldarg.0
0x5a2d  ldc.i4.s 0xFE
0x5a2f  stfld    int32 <WaitAsync>d__2::<>1__state
0x5a34  ldarg.0
0x5a35  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [mscorlib]System.TimeSpan> <WaitAsync>d__2::<>t__builder
0x5a3a  ldloc.1
0x5a3b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype [mscorlib]System.TimeSpan>::SetResult(var<u1>)
0x5a40  ret
```
