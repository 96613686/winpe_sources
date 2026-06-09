# <SerializeToStreamAsync>d__8::MoveNext

- ea: `0xc060`
- end: `0xc18d`
- name: `<SerializeToStreamAsync>d__8::MoveNext`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xbff0`
- `0xc060`

## pseudocode

```c

```

## disassembly

```asm
0xc060  ldarg.0
0xc061  ldfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc066  stloc.0
0xc067  ldarg.0
0xc068  ldfld    class System.Net.Http.PushStreamContent <SerializeToStreamAsync>d__8::<>4__this
0xc06d  stloc.1
0xc06e  ldloc.0
0xc06f  brfalse.s loc_C0DA
0xc071  ldloc.0
0xc072  ldc.i4.1
0xc073  beq      loc_C139
0xc078  ldarg.0
0xc079  newobj   instance void class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool>::.ctor()
0xc07e  stfld    class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool> <SerializeToStreamAsync>d__8::<serializeToStreamTask>5__2
0xc083  ldarg.0
0xc084  ldfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__8::stream
0xc089  ldarg.0
0xc08a  ldfld    class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool> <SerializeToStreamAsync>d__8::<serializeToStreamTask>5__2
0xc08f  newobj   instance void CompleteTaskOnCloseStream::.ctor(class [mscorlib]System.IO.Stream innerStream, class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool> serializeToStreamTask)
0xc094  stloc.2
0xc095  ldloc.1
0xc096  ldfld    class [mscorlib]System.Func`4<class [mscorlib]System.IO.Stream, class [System.Net.Http]System.Net.Http.HttpContent, class [System]System.Net.TransportContext, class [mscorlib]System.Threading.Tasks.Task> System.Net.Http.PushStreamContent::_onStreamAvailable
0xc09b  ldloc.2
0xc09c  ldloc.1
0xc09d  ldarg.0
0xc09e  ldfld    class [System]System.Net.TransportContext <SerializeToStreamAsync>d__8::context
0xc0a3  callvirt instance var<u1> class [mscorlib]System.Func`4<class [mscorlib]System.IO.Stream, class [System.Net.Http]System.Net.Http.HttpContent, class [System]System.Net.TransportContext, class [mscorlib]System.Threading.Tasks.Task>::Invoke(char, var<u1>, !!T0)
0xc0a8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xc0ad  stloc.3
0xc0ae  ldloca.s 3
0xc0b0  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xc0b5  brtrue.s loc_C0F6
0xc0b7  ldarg.0
0xc0b8  ldc.i4.0
0xc0b9  dup
0xc0ba  stloc.0
0xc0bb  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc0c0  ldarg.0
0xc0c1  ldloc.3
0xc0c2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__8::<>u__1
0xc0c7  ldarg.0
0xc0c8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__8::<>t__builder
0xc0cd  ldloca.s 3
0xc0cf  ldarg.0
0xc0d0  call     T0x2B000067
0xc0d5  leave    loc_C18C
0xc0da  ldarg.0
0xc0db  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__8::<>u__1
0xc0e0  stloc.3
0xc0e1  ldarg.0
0xc0e2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__8::<>u__1
0xc0e7  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xc0ed  ldarg.0
0xc0ee  ldc.i4.m1
0xc0ef  dup
0xc0f0  stloc.0
0xc0f1  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc0f6  ldloca.s 3
0xc0f8  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xc0fd  ldarg.0
0xc0fe  ldfld    class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool> <SerializeToStreamAsync>d__8::<serializeToStreamTask>5__2
0xc103  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool>::get_Task()
0xc108  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0xc10d  stloc.s  4
0xc10f  ldloca.s 4
0xc111  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0xc116  brtrue.s loc_C156
0xc118  ldarg.0
0xc119  ldc.i4.1
0xc11a  dup
0xc11b  stloc.0
0xc11c  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc121  ldarg.0
0xc122  ldloc.s  4
0xc124  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <SerializeToStreamAsync>d__8::<>u__2
0xc129  ldarg.0
0xc12a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__8::<>t__builder
0xc12f  ldloca.s 4
0xc131  ldarg.0
0xc132  call     T0x2B000068
0xc137  leave.s  loc_C18C
0xc139  ldarg.0
0xc13a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <SerializeToStreamAsync>d__8::<>u__2
0xc13f  stloc.s  4
0xc141  ldarg.0
0xc142  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <SerializeToStreamAsync>d__8::<>u__2
0xc147  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0xc14d  ldarg.0
0xc14e  ldc.i4.m1
0xc14f  dup
0xc150  stloc.0
0xc151  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc156  ldloca.s 4
0xc158  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0xc15d  pop
0xc15e  leave.s  loc_C179
0xc160  stloc.s  5
0xc162  ldarg.0
0xc163  ldc.i4.s 0xFE
0xc165  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc16a  ldarg.0
0xc16b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__8::<>t__builder
0xc170  ldloc.s  5
0xc172  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xc177  leave.s  loc_C18C
0xc179  ldarg.0
0xc17a  ldc.i4.s 0xFE
0xc17c  stfld    int32 <SerializeToStreamAsync>d__8::<>1__state
0xc181  ldarg.0
0xc182  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__8::<>t__builder
0xc187  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xc18c  ret
```
