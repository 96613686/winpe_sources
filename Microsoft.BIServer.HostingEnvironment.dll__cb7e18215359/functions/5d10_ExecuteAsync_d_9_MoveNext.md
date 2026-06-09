# <ExecuteAsync>d__9::MoveNext

- ea: `0x5d10`
- end: `0x5db7`
- name: `<ExecuteAsync>d__9::MoveNext`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2660`
- `0x5d10`

## pseudocode

```c

```

## disassembly

```asm
0x5d10  ldarg.0
0x5d11  ldfld    int32 <ExecuteAsync>d__9::<>1__state
0x5d16  stloc.0
0x5d17  ldarg.0
0x5d18  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteAsync>d__9::<>4__this
0x5d1d  stloc.1
0x5d1e  ldloc.0
0x5d1f  brfalse.s loc_5D63
0x5d21  ldloc.1
0x5d22  ldarg.0
0x5d23  ldfld    string <ExecuteAsync>d__9::storedProcedure
0x5d28  ldnull
0x5d29  ldarg.0
0x5d2a  ldfld    object <ExecuteAsync>d__9::parameters
0x5d2f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteAsync(string storedProcedure, class [System.Data]System.Data.IDbTransaction transaction, object parameters)
0x5d34  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x5d39  stloc.3
0x5d3a  ldloca.s 3
0x5d3c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x5d41  brtrue.s loc_5D7F
0x5d43  ldarg.0
0x5d44  ldc.i4.0
0x5d45  dup
0x5d46  stloc.0
0x5d47  stfld    int32 <ExecuteAsync>d__9::<>1__state
0x5d4c  ldarg.0
0x5d4d  ldloc.3
0x5d4e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__9::<>u__1
0x5d53  ldarg.0
0x5d54  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__9::<>t__builder
0x5d59  ldloca.s 3
0x5d5b  ldarg.0
0x5d5c  call     T0x2B00003D
0x5d61  leave.s  loc_5DB6
0x5d63  ldarg.0
0x5d64  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__9::<>u__1
0x5d69  stloc.3
0x5d6a  ldarg.0
0x5d6b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__9::<>u__1
0x5d70  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x5d76  ldarg.0
0x5d77  ldc.i4.m1
0x5d78  dup
0x5d79  stloc.0
0x5d7a  stfld    int32 <ExecuteAsync>d__9::<>1__state
0x5d7f  ldloca.s 3
0x5d81  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x5d86  stloc.2
0x5d87  leave.s  loc_5DA2
0x5d89  stloc.s  4
0x5d8b  ldarg.0
0x5d8c  ldc.i4.s 0xFE
0x5d8e  stfld    int32 <ExecuteAsync>d__9::<>1__state
0x5d93  ldarg.0
0x5d94  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__9::<>t__builder
0x5d99  ldloc.s  4
0x5d9b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x5da0  leave.s  loc_5DB6
0x5da2  ldarg.0
0x5da3  ldc.i4.s 0xFE
0x5da5  stfld    int32 <ExecuteAsync>d__9::<>1__state
0x5daa  ldarg.0
0x5dab  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__9::<>t__builder
0x5db0  ldloc.2
0x5db1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x5db6  ret
```
