# <QueryFirstOrDefaultAsync>d__12`1::MoveNext

- ea: `0x67e0`
- end: `0x6891`
- name: `<QueryFirstOrDefaultAsync>d__12`1::MoveNext`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x67e0`

## pseudocode

```c

```

## disassembly

```asm
0x67e0  ldarg.0
0x67e1  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>1__state
0x67e6  stloc.0
0x67e7  ldarg.0
0x67e8  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>4__this
0x67ed  stloc.1
0x67ee  ldloc.0
0x67ef  brfalse.s loc_683D
0x67f1  ldloc.1
0x67f2  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_connection
0x67f7  ldarg.0
0x67f8  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::storedProcedure
0x67fd  ldloc.1
0x67fe  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.BIServer.HostingEnvironment.Storage.ScopedSqlTransaction::_transaction
0x6803  ldarg.0
0x6804  ldfld    object valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::parameters
0x6809  callvirt T0x2B000044
0x680e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x6813  stloc.3
0x6814  ldloca.s 3
0x6816  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x681b  brtrue.s loc_6859
0x681d  ldarg.0
0x681e  ldc.i4.0
0x681f  dup
0x6820  stloc.0
0x6821  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>1__state
0x6826  ldarg.0
0x6827  ldloc.3
0x6828  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>u__1
0x682d  ldarg.0
0x682e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>t__builder
0x6833  ldloca.s 3
0x6835  ldarg.0
0x6836  call     T0x2B000049
0x683b  leave.s  loc_6890
0x683d  ldarg.0
0x683e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>u__1
0x6843  stloc.3
0x6844  ldarg.0
0x6845  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>u__1
0x684a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x6850  ldarg.0
0x6851  ldc.i4.m1
0x6852  dup
0x6853  stloc.0
0x6854  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>1__state
0x6859  ldloca.s 3
0x685b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x6860  stloc.2
0x6861  leave.s  loc_687C
0x6863  stloc.s  4
0x6865  ldarg.0
0x6866  ldc.i4.s 0xFE
0x6868  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>1__state
0x686d  ldarg.0
0x686e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>t__builder
0x6873  ldloc.s  4
0x6875  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x687a  leave.s  loc_6890
0x687c  ldarg.0
0x687d  ldc.i4.s 0xFE
0x687f  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>1__state
0x6884  ldarg.0
0x6885  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__12`1<var<u1>>::<>t__builder
0x688a  ldloc.2
0x688b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x6890  ret
```
