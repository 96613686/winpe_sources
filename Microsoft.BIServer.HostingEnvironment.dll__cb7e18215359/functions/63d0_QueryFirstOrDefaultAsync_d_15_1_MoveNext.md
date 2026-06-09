# <QueryFirstOrDefaultAsync>d__15`1::MoveNext

- ea: `0x63d0`
- end: `0x64ef`
- name: `<QueryFirstOrDefaultAsync>d__15`1::MoveNext`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x63d0`

## string_xrefs

- `0x64b0`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x63d0  ldarg.0
0x63d1  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>1__state
0x63d6  stloc.0
0x63d7  ldarg.0
0x63d8  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>4__this
0x63dd  stloc.1
0x63de  ldloc.0
0x63df  pop
0x63e0  nop
0x63e1  ldloc.0
0x63e2  brfalse.s loc_640E
0x63e4  ldarg.0
0x63e5  ldc.i4.3
0x63e6  newarr   [mscorlib]System.String
0x63eb  dup
0x63ec  ldc.i4.0
0x63ed  ldstr    aSql// "SQL"
0x63f2  stelem.ref
0x63f3  dup
0x63f4  ldc.i4.1
0x63f5  ldstr    aExec// "Exec"
0x63fa  stelem.ref
0x63fb  dup
0x63fc  ldc.i4.2
0x63fd  ldarg.0
0x63fe  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::storedProcedure
0x6403  stelem.ref
0x6404  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x6409  stfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>7__wrap1
0x640e  nop
0x640f  ldloc.0
0x6410  brfalse.s loc_6472
0x6412  ldloc.1
0x6413  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x6418  ldarg.0
0x6419  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::storedProcedure
0x641e  ldarg.0
0x641f  ldfld    object valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::parameters
0x6424  ldc.i4.4
0x6425  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x642a  stloc.s  4
0x642c  ldarg.0
0x642d  ldfld    class [System.Data]System.Data.IDbTransaction valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::transaction
0x6432  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x6437  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x643c  ldloc.s  4
0x643e  call     T0x2B000042
0x6443  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x6448  stloc.3
0x6449  ldloca.s 3
0x644b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x6450  brtrue.s loc_648E
0x6452  ldarg.0
0x6453  ldc.i4.0
0x6454  dup
0x6455  stloc.0
0x6456  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>1__state
0x645b  ldarg.0
0x645c  ldloc.3
0x645d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>u__1
0x6462  ldarg.0
0x6463  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>t__builder
0x6468  ldloca.s 3
0x646a  ldarg.0
0x646b  call     T0x2B000046
0x6470  leave.s  loc_64EE
0x6472  ldarg.0
0x6473  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>u__1
0x6478  stloc.3
0x6479  ldarg.0
0x647a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>u__1
0x647f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x6485  ldarg.0
0x6486  ldc.i4.m1
0x6487  dup
0x6488  stloc.0
0x6489  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>1__state
0x648e  ldloca.s 3
0x6490  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x6495  stloc.2
0x6496  leave.s  loc_64DA
0x6498  ldloc.0
0x6499  ldc.i4.0
0x649a  bge.s    loc_64AF
0x649c  ldarg.0
0x649d  ldfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>7__wrap1
0x64a2  brfalse.s loc_64AF
0x64a4  ldarg.0
0x64a5  ldfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>7__wrap1
0x64aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64af  endfinally
0x64b0  ldstr    aExceptionDurin// "Exception during db access"
0x64b5  call     T0x2B00000A
0x64ba  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x64bf  rethrow
0x64c1  stloc.s  5
0x64c3  ldarg.0
0x64c4  ldc.i4.s 0xFE
0x64c6  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>1__state
0x64cb  ldarg.0
0x64cc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>t__builder
0x64d1  ldloc.s  5
0x64d3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x64d8  leave.s  loc_64EE
0x64da  ldarg.0
0x64db  ldc.i4.s 0xFE
0x64dd  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>1__state
0x64e2  ldarg.0
0x64e3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__15`1<var<u1>>::<>t__builder
0x64e8  ldloc.2
0x64e9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x64ee  ret
```
