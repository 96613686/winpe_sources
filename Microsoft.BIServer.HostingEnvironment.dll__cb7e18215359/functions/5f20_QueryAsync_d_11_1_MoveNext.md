# <QueryAsync>d__11`1::MoveNext

- ea: `0x5f20`
- end: `0x6041`
- name: `<QueryAsync>d__11`1::MoveNext`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x2c30`
- `0x5f20`

## string_xrefs

- `0x6002`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x5f20  ldarg.0
0x5f21  ldfld    int32 valuetype <QueryAsync>d__11`1<var<u1>>::<>1__state
0x5f26  stloc.0
0x5f27  ldarg.0
0x5f28  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection valuetype <QueryAsync>d__11`1<var<u1>>::<>4__this
0x5f2d  stloc.1
0x5f2e  ldloc.0
0x5f2f  pop
0x5f30  nop
0x5f31  ldloc.0
0x5f32  brfalse.s loc_5F6A
0x5f34  ldloc.1
0x5f35  ldarg.0
0x5f36  ldfld    string valuetype <QueryAsync>d__11`1<var<u1>>::storedProcedure
0x5f3b  call     instance void Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StartStatementMeter(string storedProcedure)
0x5f40  ldarg.0
0x5f41  ldc.i4.3
0x5f42  newarr   [mscorlib]System.String
0x5f47  dup
0x5f48  ldc.i4.0
0x5f49  ldstr    aSql// "SQL"
0x5f4e  stelem.ref
0x5f4f  dup
0x5f50  ldc.i4.1
0x5f51  ldstr    aQuery// "Query"
0x5f56  stelem.ref
0x5f57  dup
0x5f58  ldc.i4.2
0x5f59  ldarg.0
0x5f5a  ldfld    string valuetype <QueryAsync>d__11`1<var<u1>>::storedProcedure
0x5f5f  stelem.ref
0x5f60  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x5f65  stfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__11`1<var<u1>>::<>7__wrap1
0x5f6a  nop
0x5f6b  ldloc.0
0x5f6c  brfalse.s loc_5FC4
0x5f6e  ldloc.1
0x5f6f  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x5f74  ldarg.0
0x5f75  ldfld    string valuetype <QueryAsync>d__11`1<var<u1>>::storedProcedure
0x5f7a  ldnull
0x5f7b  ldnull
0x5f7c  ldc.i4.4
0x5f7d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x5f82  stloc.s  4
0x5f84  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x5f89  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x5f8e  ldloc.s  4
0x5f90  call     T0x2B00003F
0x5f95  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetAwaiter()
0x5f9a  stloc.3
0x5f9b  ldloca.s 3
0x5f9d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::get_IsCompleted()
0x5fa2  brtrue.s loc_5FE0
0x5fa4  ldarg.0
0x5fa5  ldc.i4.0
0x5fa6  dup
0x5fa7  stloc.0
0x5fa8  stfld    int32 valuetype <QueryAsync>d__11`1<var<u1>>::<>1__state
0x5fad  ldarg.0
0x5fae  ldloc.3
0x5faf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>u__1
0x5fb4  ldarg.0
0x5fb5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>t__builder
0x5fba  ldloca.s 3
0x5fbc  ldarg.0
0x5fbd  call     T0x2B000040
0x5fc2  leave.s  loc_6040
0x5fc4  ldarg.0
0x5fc5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>u__1
0x5fca  stloc.3
0x5fcb  ldarg.0
0x5fcc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>u__1
0x5fd1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>
0x5fd7  ldarg.0
0x5fd8  ldc.i4.m1
0x5fd9  dup
0x5fda  stloc.0
0x5fdb  stfld    int32 valuetype <QueryAsync>d__11`1<var<u1>>::<>1__state
0x5fe0  ldloca.s 3
0x5fe2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetResult()
0x5fe7  stloc.2
0x5fe8  leave.s  loc_602C
0x5fea  ldloc.0
0x5feb  ldc.i4.0
0x5fec  bge.s    loc_6001
0x5fee  ldarg.0
0x5fef  ldfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__11`1<var<u1>>::<>7__wrap1
0x5ff4  brfalse.s loc_6001
0x5ff6  ldarg.0
0x5ff7  ldfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__11`1<var<u1>>::<>7__wrap1
0x5ffc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6001  endfinally
0x6002  ldstr    aExceptionDurin// "Exception during db access"
0x6007  call     T0x2B00000A
0x600c  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x6011  rethrow
0x6013  stloc.s  5
0x6015  ldarg.0
0x6016  ldc.i4.s 0xFE
0x6018  stfld    int32 valuetype <QueryAsync>d__11`1<var<u1>>::<>1__state
0x601d  ldarg.0
0x601e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>t__builder
0x6023  ldloc.s  5
0x6025  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::SetException(class [mscorlib]System.Exception)
0x602a  leave.s  loc_6040
0x602c  ldarg.0
0x602d  ldc.i4.s 0xFE
0x602f  stfld    int32 valuetype <QueryAsync>d__11`1<var<u1>>::<>1__state
0x6034  ldarg.0
0x6035  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__11`1<var<u1>>::<>t__builder
0x603a  ldloc.2
0x603b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::SetResult(var<u1>)
0x6040  ret
```
