# <CastToObject>d__0::MoveNext

- ea: `0xe280`
- end: `0xe312`
- name: `<CastToObject>d__0::MoveNext`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe280`

## pseudocode

```c

```

## disassembly

```asm
0xe280  ldarg.0
0xe281  ldfld    int32 <CastToObject>d__0::<>1__state
0xe286  stloc.0
0xe287  ldloc.0
0xe288  brfalse.s loc_E2BF
0xe28a  ldarg.0
0xe28b  ldfld    class [mscorlib]System.Threading.Tasks.Task <CastToObject>d__0::task
0xe290  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xe295  stloc.2
0xe296  ldloca.s 2
0xe298  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xe29d  brtrue.s loc_E2DB
0xe29f  ldarg.0
0xe2a0  ldc.i4.0
0xe2a1  dup
0xe2a2  stloc.0
0xe2a3  stfld    int32 <CastToObject>d__0::<>1__state
0xe2a8  ldarg.0
0xe2a9  ldloc.2
0xe2aa  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CastToObject>d__0::<>u__1
0xe2af  ldarg.0
0xe2b0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <CastToObject>d__0::<>t__builder
0xe2b5  ldloca.s 2
0xe2b7  ldarg.0
0xe2b8  call     T0x2B00007B
0xe2bd  leave.s  loc_E311
0xe2bf  ldarg.0
0xe2c0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CastToObject>d__0::<>u__1
0xe2c5  stloc.2
0xe2c6  ldarg.0
0xe2c7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CastToObject>d__0::<>u__1
0xe2cc  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xe2d2  ldarg.0
0xe2d3  ldc.i4.m1
0xe2d4  dup
0xe2d5  stloc.0
0xe2d6  stfld    int32 <CastToObject>d__0::<>1__state
0xe2db  ldloca.s 2
0xe2dd  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xe2e2  ldnull
0xe2e3  stloc.1
0xe2e4  leave.s  loc_E2FD
0xe2e6  stloc.3
0xe2e7  ldarg.0
0xe2e8  ldc.i4.s 0xFE
0xe2ea  stfld    int32 <CastToObject>d__0::<>1__state
0xe2ef  ldarg.0
0xe2f0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <CastToObject>d__0::<>t__builder
0xe2f5  ldloc.3
0xe2f6  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetException(class [mscorlib]System.Exception)
0xe2fb  leave.s  loc_E311
0xe2fd  ldarg.0
0xe2fe  ldc.i4.s 0xFE
0xe300  stfld    int32 <CastToObject>d__0::<>1__state
0xe305  ldarg.0
0xe306  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <CastToObject>d__0::<>t__builder
0xe30b  ldloc.1
0xe30c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetResult(var<u1>)
0xe311  ret
```
