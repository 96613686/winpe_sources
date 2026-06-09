# <ExecuteAsync>d__7::MoveNext

- ea: `0x6700`
- end: `0x67b1`
- name: `<ExecuteAsync>d__7::MoveNext`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2660`
- `0x6700`

## pseudocode

```c

```

## disassembly

```asm
0x6700  ldarg.0
0x6701  ldfld    int32 <ExecuteAsync>d__7::<>1__state
0x6706  stloc.0
0x6707  ldarg.0
0x6708  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction <ExecuteAsync>d__7::<>4__this
0x670d  stloc.1
0x670e  ldloc.0
0x670f  brfalse.s loc_675D
0x6711  ldloc.1
0x6712  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_connection
0x6717  ldarg.0
0x6718  ldfld    string <ExecuteAsync>d__7::storedProcedure
0x671d  ldloc.1
0x671e  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_transaction
0x6723  ldarg.0
0x6724  ldfld    object <ExecuteAsync>d__7::parameters
0x6729  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteAsync(string storedProcedure, class [System.Data]System.Data.IDbTransaction transaction, object parameters)
0x672e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x6733  stloc.3
0x6734  ldloca.s 3
0x6736  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x673b  brtrue.s loc_6779
0x673d  ldarg.0
0x673e  ldc.i4.0
0x673f  dup
0x6740  stloc.0
0x6741  stfld    int32 <ExecuteAsync>d__7::<>1__state
0x6746  ldarg.0
0x6747  ldloc.3
0x6748  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__7::<>u__1
0x674d  ldarg.0
0x674e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__7::<>t__builder
0x6753  ldloca.s 3
0x6755  ldarg.0
0x6756  call     T0x2B000048
0x675b  leave.s  loc_67B0
0x675d  ldarg.0
0x675e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__7::<>u__1
0x6763  stloc.3
0x6764  ldarg.0
0x6765  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__7::<>u__1
0x676a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x6770  ldarg.0
0x6771  ldc.i4.m1
0x6772  dup
0x6773  stloc.0
0x6774  stfld    int32 <ExecuteAsync>d__7::<>1__state
0x6779  ldloca.s 3
0x677b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x6780  stloc.2
0x6781  leave.s  loc_679C
0x6783  stloc.s  4
0x6785  ldarg.0
0x6786  ldc.i4.s 0xFE
0x6788  stfld    int32 <ExecuteAsync>d__7::<>1__state
0x678d  ldarg.0
0x678e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__7::<>t__builder
0x6793  ldloc.s  4
0x6795  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x679a  leave.s  loc_67B0
0x679c  ldarg.0
0x679d  ldc.i4.s 0xFE
0x679f  stfld    int32 <ExecuteAsync>d__7::<>1__state
0x67a4  ldarg.0
0x67a5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__7::<>t__builder
0x67aa  ldloc.2
0x67ab  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x67b0  ret
```
