# <QueryFirstOrDefaultAsync>d__13`1::MoveNext

- ea: `0x61c0`
- end: `0x62d5`
- name: `<QueryFirstOrDefaultAsync>d__13`1::MoveNext`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x61c0`

## string_xrefs

- `0x6296`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x61c0  ldarg.0
0x61c1  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>1__state
0x61c6  stloc.0
0x61c7  ldarg.0
0x61c8  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>4__this
0x61cd  stloc.1
0x61ce  ldloc.0
0x61cf  pop
0x61d0  nop
0x61d1  ldloc.0
0x61d2  brfalse.s loc_61FE
0x61d4  ldarg.0
0x61d5  ldc.i4.3
0x61d6  newarr   [mscorlib]System.String
0x61db  dup
0x61dc  ldc.i4.0
0x61dd  ldstr    aSql// "SQL"
0x61e2  stelem.ref
0x61e3  dup
0x61e4  ldc.i4.1
0x61e5  ldstr    aExec// "Exec"
0x61ea  stelem.ref
0x61eb  dup
0x61ec  ldc.i4.2
0x61ed  ldarg.0
0x61ee  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::storedProcedure
0x61f3  stelem.ref
0x61f4  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x61f9  stfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>7__wrap1
0x61fe  nop
0x61ff  ldloc.0
0x6200  brfalse.s loc_6258
0x6202  ldloc.1
0x6203  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x6208  ldarg.0
0x6209  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::storedProcedure
0x620e  ldnull
0x620f  ldnull
0x6210  ldc.i4.4
0x6211  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x6216  stloc.s  4
0x6218  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x621d  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x6222  ldloc.s  4
0x6224  call     T0x2B000042
0x6229  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x622e  stloc.3
0x622f  ldloca.s 3
0x6231  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x6236  brtrue.s loc_6274
0x6238  ldarg.0
0x6239  ldc.i4.0
0x623a  dup
0x623b  stloc.0
0x623c  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>1__state
0x6241  ldarg.0
0x6242  ldloc.3
0x6243  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>u__1
0x6248  ldarg.0
0x6249  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>t__builder
0x624e  ldloca.s 3
0x6250  ldarg.0
0x6251  call     T0x2B000043
0x6256  leave.s  loc_62D4
0x6258  ldarg.0
0x6259  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>u__1
0x625e  stloc.3
0x625f  ldarg.0
0x6260  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>u__1
0x6265  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x626b  ldarg.0
0x626c  ldc.i4.m1
0x626d  dup
0x626e  stloc.0
0x626f  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>1__state
0x6274  ldloca.s 3
0x6276  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x627b  stloc.2
0x627c  leave.s  loc_62C0
0x627e  ldloc.0
0x627f  ldc.i4.0
0x6280  bge.s    loc_6295
0x6282  ldarg.0
0x6283  ldfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>7__wrap1
0x6288  brfalse.s loc_6295
0x628a  ldarg.0
0x628b  ldfld    class [mscorlib]System.IDisposable valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>7__wrap1
0x6290  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6295  endfinally
0x6296  ldstr    aExceptionDurin// "Exception during db access"
0x629b  call     T0x2B00000A
0x62a0  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x62a5  rethrow
0x62a7  stloc.s  5
0x62a9  ldarg.0
0x62aa  ldc.i4.s 0xFE
0x62ac  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>1__state
0x62b1  ldarg.0
0x62b2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>t__builder
0x62b7  ldloc.s  5
0x62b9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x62be  leave.s  loc_62D4
0x62c0  ldarg.0
0x62c1  ldc.i4.s 0xFE
0x62c3  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>1__state
0x62c8  ldarg.0
0x62c9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__13`1<var<u1>>::<>t__builder
0x62ce  ldloc.2
0x62cf  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x62d4  ret
```
