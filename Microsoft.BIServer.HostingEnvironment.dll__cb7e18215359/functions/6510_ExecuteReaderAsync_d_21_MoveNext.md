# <ExecuteReaderAsync>d__21::MoveNext

- ea: `0x6510`
- end: `0x66d3`
- name: `<ExecuteReaderAsync>d__21::MoveNext`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x15d0`
- `0x1be0`
- `0x2c30`
- `0x6510`

## string_xrefs

- `0x668e`: `Error executing SQL command. Details:{0}`
- `0x6541`: `Reader`

## pseudocode

```c

```

## disassembly

```asm
0x6510  ldarg.0
0x6511  ldfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x6516  stloc.0
0x6517  ldarg.0
0x6518  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteReaderAsync>d__21::<>4__this
0x651d  stloc.1
0x651e  ldloc.0
0x651f  pop
0x6520  nop
0x6521  ldloc.0
0x6522  brfalse.s loc_655A
0x6524  ldloc.1
0x6525  ldarg.0
0x6526  ldfld    string <ExecuteReaderAsync>d__21::storedProcedure
0x652b  call     instance void Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StartStatementMeter(string storedProcedure)
0x6530  ldarg.0
0x6531  ldc.i4.3
0x6532  newarr   [mscorlib]System.String
0x6537  dup
0x6538  ldc.i4.0
0x6539  ldstr    aSql// "SQL"
0x653e  stelem.ref
0x653f  dup
0x6540  ldc.i4.1
0x6541  ldstr    aReader// "Reader"
0x6546  stelem.ref
0x6547  dup
0x6548  ldc.i4.2
0x6549  ldarg.0
0x654a  ldfld    string <ExecuteReaderAsync>d__21::storedProcedure
0x654f  stelem.ref
0x6550  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x6555  stfld    class [mscorlib]System.IDisposable <ExecuteReaderAsync>d__21::<>7__wrap1
0x655a  nop
0x655b  ldloc.0
0x655c  brfalse.s loc_6575
0x655e  ldarg.0
0x655f  ldarg.0
0x6560  ldfld    string <ExecuteReaderAsync>d__21::storedProcedure
0x6565  ldloc.1
0x6566  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x656b  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x6570  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x6575  nop
0x6576  ldloc.0
0x6577  brfalse  loc_6635
0x657c  ldarg.0
0x657d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <ExecuteReaderAsync>d__21::parameters
0x6582  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x6587  stloc.3
0x6588  br.s     loc_65B7
0x658a  ldloca.s 3
0x658c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x6591  stloc.s  4
0x6593  ldarg.0
0x6594  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x6599  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x659e  ldloca.s 4
0x65a0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x65a5  ldloca.s 4
0x65a7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x65ac  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, object)
0x65b1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x65b6  pop
0x65b7  ldloca.s 3
0x65b9  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x65be  brtrue.s loc_658A
0x65c0  leave.s  loc_65D4
0x65c2  ldloc.0
0x65c3  ldc.i4.0
0x65c4  bge.s    loc_65D3
0x65c6  ldloca.s 3
0x65c8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x65ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65d3  endfinally
0x65d4  ldarg.0
0x65d5  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x65da  ldc.i4.4
0x65db  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x65e0  ldarg.0
0x65e1  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x65e6  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x65eb  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x65f0  ldarg.0
0x65f1  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x65f6  ldarg.0
0x65f7  ldfld    valuetype [System.Data]System.Data.CommandBehavior <ExecuteReaderAsync>d__21::commandBehavior
0x65fc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::ExecuteReaderAsync(valuetype [System.Data]System.Data.CommandBehavior)
0x6601  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::GetAwaiter()
0x6606  stloc.s  5
0x6608  ldloca.s 5
0x660a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::get_IsCompleted()
0x660f  brtrue.s loc_6652
0x6611  ldarg.0
0x6612  ldc.i4.0
0x6613  dup
0x6614  stloc.0
0x6615  stfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x661a  ldarg.0
0x661b  ldloc.s  5
0x661d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> <ExecuteReaderAsync>d__21::<>u__1
0x6622  ldarg.0
0x6623  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x6628  ldloca.s 5
0x662a  ldarg.0
0x662b  call     T0x2B000047
0x6630  leave    loc_66D2
0x6635  ldarg.0
0x6636  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> <ExecuteReaderAsync>d__21::<>u__1
0x663b  stloc.s  5
0x663d  ldarg.0
0x663e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> <ExecuteReaderAsync>d__21::<>u__1
0x6643  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>
0x6649  ldarg.0
0x664a  ldc.i4.m1
0x664b  dup
0x664c  stloc.0
0x664d  stfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x6652  ldloca.s 5
0x6654  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::GetResult()
0x6659  stloc.2
0x665a  leave.s  loc_66BE
0x665c  ldloc.0
0x665d  ldc.i4.0
0x665e  bge.s    loc_6673
0x6660  ldarg.0
0x6661  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x6666  brfalse.s loc_6673
0x6668  ldarg.0
0x6669  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand <ExecuteReaderAsync>d__21::<cmd>5__3
0x666e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6673  endfinally
0x6674  ldloc.0
0x6675  ldc.i4.0
0x6676  bge.s    loc_668B
0x6678  ldarg.0
0x6679  ldfld    class [mscorlib]System.IDisposable <ExecuteReaderAsync>d__21::<>7__wrap1
0x667e  brfalse.s loc_668B
0x6680  ldarg.0
0x6681  ldfld    class [mscorlib]System.IDisposable <ExecuteReaderAsync>d__21::<>7__wrap1
0x6686  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x668b  endfinally
0x668c  stloc.s  6
0x668e  ldstr    aErrorExecuting// "Error executing SQL command. Details:{0"...
0x6693  ldc.i4.1
0x6694  newarr   [mscorlib]System.Object
0x6699  dup
0x669a  ldc.i4.0
0x669b  ldloc.s  6
0x669d  stelem.ref
0x669e  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x66a3  rethrow
0x66a5  stloc.s  7
0x66a7  ldarg.0
0x66a8  ldc.i4.s 0xFE
0x66aa  stfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x66af  ldarg.0
0x66b0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x66b5  ldloc.s  7
0x66b7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader>::SetException(class [mscorlib]System.Exception)
0x66bc  leave.s  loc_66D2
0x66be  ldarg.0
0x66bf  ldc.i4.s 0xFE
0x66c1  stfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x66c6  ldarg.0
0x66c7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x66cc  ldloc.2
0x66cd  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader>::SetResult(var<u1>)
0x66d2  ret
```
