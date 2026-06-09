# <CastToObject>d__1`1::MoveNext

- ea: `0xe340`
- end: `0xe3d6`
- name: `<CastToObject>d__1`1::MoveNext`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe340`

## pseudocode

```c

```

## disassembly

```asm
0xe340  ldarg.0
0xe341  ldfld    int32 valuetype <CastToObject>d__1`1<var<u1>>::<>1__state
0xe346  stloc.0
0xe347  ldloc.0
0xe348  brfalse.s loc_E37F
0xe34a  ldarg.0
0xe34b  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype <CastToObject>d__1`1<var<u1>>::task
0xe350  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0xe355  stloc.2
0xe356  ldloca.s 2
0xe358  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0xe35d  brtrue.s loc_E39B
0xe35f  ldarg.0
0xe360  ldc.i4.0
0xe361  dup
0xe362  stloc.0
0xe363  stfld    int32 valuetype <CastToObject>d__1`1<var<u1>>::<>1__state
0xe368  ldarg.0
0xe369  ldloc.2
0xe36a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <CastToObject>d__1`1<var<u1>>::<>u__1
0xe36f  ldarg.0
0xe370  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> valuetype <CastToObject>d__1`1<var<u1>>::<>t__builder
0xe375  ldloca.s 2
0xe377  ldarg.0
0xe378  call     T0x2B00007C
0xe37d  leave.s  loc_E3D5
0xe37f  ldarg.0
0xe380  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <CastToObject>d__1`1<var<u1>>::<>u__1
0xe385  stloc.2
0xe386  ldarg.0
0xe387  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <CastToObject>d__1`1<var<u1>>::<>u__1
0xe38c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0xe392  ldarg.0
0xe393  ldc.i4.m1
0xe394  dup
0xe395  stloc.0
0xe396  stfld    int32 valuetype <CastToObject>d__1`1<var<u1>>::<>1__state
0xe39b  ldloca.s 2
0xe39d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0xe3a2  box      var<u1>
0xe3a7  stloc.1
0xe3a8  leave.s  loc_E3C1
0xe3aa  stloc.3
0xe3ab  ldarg.0
0xe3ac  ldc.i4.s 0xFE
0xe3ae  stfld    int32 valuetype <CastToObject>d__1`1<var<u1>>::<>1__state
0xe3b3  ldarg.0
0xe3b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> valuetype <CastToObject>d__1`1<var<u1>>::<>t__builder
0xe3b9  ldloc.3
0xe3ba  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetException(class [mscorlib]System.Exception)
0xe3bf  leave.s  loc_E3D5
0xe3c1  ldarg.0
0xe3c2  ldc.i4.s 0xFE
0xe3c4  stfld    int32 valuetype <CastToObject>d__1`1<var<u1>>::<>1__state
0xe3c9  ldarg.0
0xe3ca  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> valuetype <CastToObject>d__1`1<var<u1>>::<>t__builder
0xe3cf  ldloc.1
0xe3d0  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetResult(var<u1>)
0xe3d5  ret
```
