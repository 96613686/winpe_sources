# <ExecuteAsync>d__8::MoveNext

- ea: `0x5bd0`
- end: `0x5ce5`
- name: `<ExecuteAsync>d__8::MoveNext`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x5bd0`

## string_xrefs

- `0x5ca6`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x5bd0  ldarg.0
0x5bd1  ldfld    int32 <ExecuteAsync>d__8::<>1__state
0x5bd6  stloc.0
0x5bd7  ldarg.0
0x5bd8  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteAsync>d__8::<>4__this
0x5bdd  stloc.1
0x5bde  ldloc.0
0x5bdf  pop
0x5be0  nop
0x5be1  ldloc.0
0x5be2  brfalse.s loc_5C0E
0x5be4  ldarg.0
0x5be5  ldc.i4.3
0x5be6  newarr   [mscorlib]System.String
0x5beb  dup
0x5bec  ldc.i4.0
0x5bed  ldstr    aSql// "SQL"
0x5bf2  stelem.ref
0x5bf3  dup
0x5bf4  ldc.i4.1
0x5bf5  ldstr    aExec// "Exec"
0x5bfa  stelem.ref
0x5bfb  dup
0x5bfc  ldc.i4.2
0x5bfd  ldarg.0
0x5bfe  ldfld    string <ExecuteAsync>d__8::storedProcedure
0x5c03  stelem.ref
0x5c04  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x5c09  stfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__8::<>7__wrap1
0x5c0e  nop
0x5c0f  ldloc.0
0x5c10  brfalse.s loc_5C68
0x5c12  ldloc.1
0x5c13  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x5c18  ldarg.0
0x5c19  ldfld    string <ExecuteAsync>d__8::storedProcedure
0x5c1e  ldnull
0x5c1f  ldnull
0x5c20  ldc.i4.4
0x5c21  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x5c26  stloc.s  4
0x5c28  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x5c2d  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x5c32  ldloc.s  4
0x5c34  call     class [mscorlib]System.Threading.Tasks.Task`1<int32> [Dapper.StrongName]Dapper.SqlMapper::ExecuteAsync(class [System.Data]System.Data.IDbConnection, string, object, class [System.Data]System.Data.IDbTransaction, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>)
0x5c39  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x5c3e  stloc.3
0x5c3f  ldloca.s 3
0x5c41  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x5c46  brtrue.s loc_5C84
0x5c48  ldarg.0
0x5c49  ldc.i4.0
0x5c4a  dup
0x5c4b  stloc.0
0x5c4c  stfld    int32 <ExecuteAsync>d__8::<>1__state
0x5c51  ldarg.0
0x5c52  ldloc.3
0x5c53  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__8::<>u__1
0x5c58  ldarg.0
0x5c59  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__8::<>t__builder
0x5c5e  ldloca.s 3
0x5c60  ldarg.0
0x5c61  call     T0x2B00003C
0x5c66  leave.s  loc_5CE4
0x5c68  ldarg.0
0x5c69  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__8::<>u__1
0x5c6e  stloc.3
0x5c6f  ldarg.0
0x5c70  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__8::<>u__1
0x5c75  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x5c7b  ldarg.0
0x5c7c  ldc.i4.m1
0x5c7d  dup
0x5c7e  stloc.0
0x5c7f  stfld    int32 <ExecuteAsync>d__8::<>1__state
0x5c84  ldloca.s 3
0x5c86  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x5c8b  stloc.2
0x5c8c  leave.s  loc_5CD0
0x5c8e  ldloc.0
0x5c8f  ldc.i4.0
0x5c90  bge.s    loc_5CA5
0x5c92  ldarg.0
0x5c93  ldfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__8::<>7__wrap1
0x5c98  brfalse.s loc_5CA5
0x5c9a  ldarg.0
0x5c9b  ldfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__8::<>7__wrap1
0x5ca0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ca5  endfinally
0x5ca6  ldstr    aExceptionDurin// "Exception during db access"
0x5cab  call     T0x2B00000A
0x5cb0  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x5cb5  rethrow
0x5cb7  stloc.s  5
0x5cb9  ldarg.0
0x5cba  ldc.i4.s 0xFE
0x5cbc  stfld    int32 <ExecuteAsync>d__8::<>1__state
0x5cc1  ldarg.0
0x5cc2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__8::<>t__builder
0x5cc7  ldloc.s  5
0x5cc9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x5cce  leave.s  loc_5CE4
0x5cd0  ldarg.0
0x5cd1  ldc.i4.s 0xFE
0x5cd3  stfld    int32 <ExecuteAsync>d__8::<>1__state
0x5cd8  ldarg.0
0x5cd9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__8::<>t__builder
0x5cde  ldloc.2
0x5cdf  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x5ce4  ret
```
