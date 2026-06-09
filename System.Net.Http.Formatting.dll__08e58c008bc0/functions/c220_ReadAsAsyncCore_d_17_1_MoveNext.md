# <ReadAsAsyncCore>d__17`1::MoveNext

- ea: `0xc220`
- end: `0xc34c`
- name: `<ReadAsAsyncCore>d__17`1::MoveNext`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x7f40`
- `0xc220`

## pseudocode

```c

```

## disassembly

```asm
0xc220  ldarg.0
0xc221  ldfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc226  stloc.0
0xc227  ldloc.0
0xc228  brfalse.s loc_C279
0xc22a  ldloc.0
0xc22b  ldc.i4.1
0xc22c  beq      loc_C2F2
0xc231  ldarg.0
0xc232  ldflda   valuetype [mscorlib]System.Threading.CancellationToken valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::cancellationToken
0xc237  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xc23c  ldarg.0
0xc23d  ldfld    class [System.Net.Http]System.Net.Http.HttpContent valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::content
0xc242  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStreamAsync()
0xc247  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xc24c  stloc.3
0xc24d  ldloca.s 3
0xc24f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xc254  brtrue.s loc_C295
0xc256  ldarg.0
0xc257  ldc.i4.0
0xc258  dup
0xc259  stloc.0
0xc25a  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc25f  ldarg.0
0xc260  ldloc.3
0xc261  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__1
0xc266  ldarg.0
0xc267  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>t__builder
0xc26c  ldloca.s 3
0xc26e  ldarg.0
0xc26f  call     T0x2B00006A
0xc274  leave    loc_C34B
0xc279  ldarg.0
0xc27a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__1
0xc27f  stloc.3
0xc280  ldarg.0
0xc281  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__1
0xc286  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xc28c  ldarg.0
0xc28d  ldc.i4.m1
0xc28e  dup
0xc28f  stloc.0
0xc290  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc295  ldloca.s 3
0xc297  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xc29c  stloc.2
0xc29d  ldarg.0
0xc29e  ldfld    class System.Net.Http.Formatting.MediaTypeFormatter valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::formatter
0xc2a3  ldarg.0
0xc2a4  ldfld    class [mscorlib]System.Type valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::type
0xc2a9  ldloc.2
0xc2aa  ldarg.0
0xc2ab  ldfld    class [System.Net.Http]System.Net.Http.HttpContent valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::content
0xc2b0  ldarg.0
0xc2b1  ldfld    class System.Net.Http.Formatting.IFormatterLogger valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::formatterLogger
0xc2b6  ldarg.0
0xc2b7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::cancellationToken
0xc2bc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<object> System.Net.Http.Formatting.MediaTypeFormatter::ReadFromStreamAsync(class [mscorlib]System.Type type, class [mscorlib]System.IO.Stream readStream, class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.IFormatterLogger formatterLogger, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xc2c1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<object>::GetAwaiter()
0xc2c6  stloc.s  4
0xc2c8  ldloca.s 4
0xc2ca  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object>::get_IsCompleted()
0xc2cf  brtrue.s loc_C30F
0xc2d1  ldarg.0
0xc2d2  ldc.i4.1
0xc2d3  dup
0xc2d4  stloc.0
0xc2d5  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc2da  ldarg.0
0xc2db  ldloc.s  4
0xc2dd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__2
0xc2e2  ldarg.0
0xc2e3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>t__builder
0xc2e8  ldloca.s 4
0xc2ea  ldarg.0
0xc2eb  call     T0x2B00006B
0xc2f0  leave.s  loc_C34B
0xc2f2  ldarg.0
0xc2f3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__2
0xc2f8  stloc.s  4
0xc2fa  ldarg.0
0xc2fb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>u__2
0xc300  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object>
0xc306  ldarg.0
0xc307  ldc.i4.m1
0xc308  dup
0xc309  stloc.0
0xc30a  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc30f  ldloca.s 4
0xc311  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<object>::GetResult()
0xc316  unbox.any var<u1>
0xc31b  stloc.1
0xc31c  leave.s  loc_C337
0xc31e  stloc.s  5
0xc320  ldarg.0
0xc321  ldc.i4.s 0xFE
0xc323  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc328  ldarg.0
0xc329  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>t__builder
0xc32e  ldloc.s  5
0xc330  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0xc335  leave.s  loc_C34B
0xc337  ldarg.0
0xc338  ldc.i4.s 0xFE
0xc33a  stfld    int32 valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>1__state
0xc33f  ldarg.0
0xc340  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsAsyncCore>d__17`1<var<u1>>::<>t__builder
0xc345  ldloc.1
0xc346  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0xc34b  ret
```
