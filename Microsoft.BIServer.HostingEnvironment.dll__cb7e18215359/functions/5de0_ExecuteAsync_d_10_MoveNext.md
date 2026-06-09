# <ExecuteAsync>d__10::MoveNext

- ea: `0x5de0`
- end: `0x5eff`
- name: `<ExecuteAsync>d__10::MoveNext`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x5de0`

## string_xrefs

- `0x5ec0`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x5de0  ldarg.0
0x5de1  ldfld    int32 <ExecuteAsync>d__10::<>1__state
0x5de6  stloc.0
0x5de7  ldarg.0
0x5de8  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteAsync>d__10::<>4__this
0x5ded  stloc.1
0x5dee  ldloc.0
0x5def  pop
0x5df0  nop
0x5df1  ldloc.0
0x5df2  brfalse.s loc_5E1E
0x5df4  ldarg.0
0x5df5  ldc.i4.3
0x5df6  newarr   [mscorlib]System.String
0x5dfb  dup
0x5dfc  ldc.i4.0
0x5dfd  ldstr    aSql// "SQL"
0x5e02  stelem.ref
0x5e03  dup
0x5e04  ldc.i4.1
0x5e05  ldstr    aExec// "Exec"
0x5e0a  stelem.ref
0x5e0b  dup
0x5e0c  ldc.i4.2
0x5e0d  ldarg.0
0x5e0e  ldfld    string <ExecuteAsync>d__10::storedProcedure
0x5e13  stelem.ref
0x5e14  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x5e19  stfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__10::<>7__wrap1
0x5e1e  nop
0x5e1f  ldloc.0
0x5e20  brfalse.s loc_5E82
0x5e22  ldloc.1
0x5e23  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x5e28  ldarg.0
0x5e29  ldfld    string <ExecuteAsync>d__10::storedProcedure
0x5e2e  ldarg.0
0x5e2f  ldfld    object <ExecuteAsync>d__10::parameters
0x5e34  ldarg.0
0x5e35  ldfld    class [System.Data]System.Data.IDbTransaction <ExecuteAsync>d__10::transaction
0x5e3a  ldc.i4.4
0x5e3b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x5e40  stloc.s  4
0x5e42  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x5e47  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x5e4c  ldloc.s  4
0x5e4e  call     class [mscorlib]System.Threading.Tasks.Task`1<int32> [Dapper.StrongName]Dapper.SqlMapper::ExecuteAsync(class [System.Data]System.Data.IDbConnection, string, object, class [System.Data]System.Data.IDbTransaction, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>)
0x5e53  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x5e58  stloc.3
0x5e59  ldloca.s 3
0x5e5b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x5e60  brtrue.s loc_5E9E
0x5e62  ldarg.0
0x5e63  ldc.i4.0
0x5e64  dup
0x5e65  stloc.0
0x5e66  stfld    int32 <ExecuteAsync>d__10::<>1__state
0x5e6b  ldarg.0
0x5e6c  ldloc.3
0x5e6d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__10::<>u__1
0x5e72  ldarg.0
0x5e73  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x5e78  ldloca.s 3
0x5e7a  ldarg.0
0x5e7b  call     T0x2B00003E
0x5e80  leave.s  loc_5EFE
0x5e82  ldarg.0
0x5e83  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__10::<>u__1
0x5e88  stloc.3
0x5e89  ldarg.0
0x5e8a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__10::<>u__1
0x5e8f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x5e95  ldarg.0
0x5e96  ldc.i4.m1
0x5e97  dup
0x5e98  stloc.0
0x5e99  stfld    int32 <ExecuteAsync>d__10::<>1__state
0x5e9e  ldloca.s 3
0x5ea0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x5ea5  stloc.2
0x5ea6  leave.s  loc_5EEA
0x5ea8  ldloc.0
0x5ea9  ldc.i4.0
0x5eaa  bge.s    loc_5EBF
0x5eac  ldarg.0
0x5ead  ldfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__10::<>7__wrap1
0x5eb2  brfalse.s loc_5EBF
0x5eb4  ldarg.0
0x5eb5  ldfld    class [mscorlib]System.IDisposable <ExecuteAsync>d__10::<>7__wrap1
0x5eba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ebf  endfinally
0x5ec0  ldstr    aExceptionDurin// "Exception during db access"
0x5ec5  call     T0x2B00000A
0x5eca  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x5ecf  rethrow
0x5ed1  stloc.s  5
0x5ed3  ldarg.0
0x5ed4  ldc.i4.s 0xFE
0x5ed6  stfld    int32 <ExecuteAsync>d__10::<>1__state
0x5edb  ldarg.0
0x5edc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x5ee1  ldloc.s  5
0x5ee3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x5ee8  leave.s  loc_5EFE
0x5eea  ldarg.0
0x5eeb  ldc.i4.s 0xFE
0x5eed  stfld    int32 <ExecuteAsync>d__10::<>1__state
0x5ef2  ldarg.0
0x5ef3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x5ef8  ldloc.2
0x5ef9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x5efe  ret
```
