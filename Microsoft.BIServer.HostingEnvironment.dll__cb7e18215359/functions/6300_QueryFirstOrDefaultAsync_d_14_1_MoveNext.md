# <QueryFirstOrDefaultAsync>d__14`1::MoveNext

- ea: `0x6300`
- end: `0x63a7`
- name: `<QueryFirstOrDefaultAsync>d__14`1::MoveNext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6300`

## pseudocode

```c

```

## disassembly

```asm
0x6300  ldarg.0
0x6301  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>1__state
0x6306  stloc.0
0x6307  ldarg.0
0x6308  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>4__this
0x630d  stloc.1
0x630e  ldloc.0
0x630f  brfalse.s loc_6353
0x6311  ldloc.1
0x6312  ldarg.0
0x6313  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::storedProcedure
0x6318  ldnull
0x6319  ldarg.0
0x631a  ldfld    object valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::parameters
0x631f  call     T0x2B000044
0x6324  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x6329  stloc.3
0x632a  ldloca.s 3
0x632c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x6331  brtrue.s loc_636F
0x6333  ldarg.0
0x6334  ldc.i4.0
0x6335  dup
0x6336  stloc.0
0x6337  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>1__state
0x633c  ldarg.0
0x633d  ldloc.3
0x633e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>u__1
0x6343  ldarg.0
0x6344  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>t__builder
0x6349  ldloca.s 3
0x634b  ldarg.0
0x634c  call     T0x2B000045
0x6351  leave.s  loc_63A6
0x6353  ldarg.0
0x6354  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>u__1
0x6359  stloc.3
0x635a  ldarg.0
0x635b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>u__1
0x6360  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x6366  ldarg.0
0x6367  ldc.i4.m1
0x6368  dup
0x6369  stloc.0
0x636a  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>1__state
0x636f  ldloca.s 3
0x6371  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x6376  stloc.2
0x6377  leave.s  loc_6392
0x6379  stloc.s  4
0x637b  ldarg.0
0x637c  ldc.i4.s 0xFE
0x637e  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>1__state
0x6383  ldarg.0
0x6384  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>t__builder
0x6389  ldloc.s  4
0x638b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x6390  leave.s  loc_63A6
0x6392  ldarg.0
0x6393  ldc.i4.s 0xFE
0x6395  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>1__state
0x639a  ldarg.0
0x639b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__14`1<var<u1>>::<>t__builder
0x63a0  ldloc.2
0x63a1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x63a6  ret
```
