# Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteScalar

- ea: `0x2a20`
- end: `0x2ae0`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteScalar`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x15d0`
- `0x1be0`
- `0x2a20`

## string_xrefs

- `0x2ac6`: `Error executing SQL command. Details:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x2a20  ldc.i4.3
0x2a21  newarr   [mscorlib]System.String
0x2a26  dup
0x2a27  ldc.i4.0
0x2a28  ldstr    aSql// "SQL"
0x2a2d  stelem.ref
0x2a2e  dup
0x2a2f  ldc.i4.1
0x2a30  ldstr    aExec// "Exec"
0x2a35  stelem.ref
0x2a36  dup
0x2a37  ldc.i4.2
0x2a38  ldarg.1
0x2a39  stelem.ref
0x2a3a  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x2a3f  stloc.0
0x2a40  ldarg.1
0x2a41  ldarg.0
0x2a42  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x2a47  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x2a4c  stloc.1
0x2a4d  ldarg.2
0x2a4e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x2a53  stloc.2
0x2a54  br.s     loc_2A7D
0x2a56  ldloca.s 2
0x2a58  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x2a5d  stloc.3
0x2a5e  ldloc.1
0x2a5f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x2a64  ldloca.s 3
0x2a66  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2a6b  ldloca.s 3
0x2a6d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2a72  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2a77  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x2a7c  pop
0x2a7d  ldloca.s 2
0x2a7f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x2a84  brtrue.s loc_2A56
0x2a86  leave.s  loc_2A96
0x2a88  ldloca.s 2
0x2a8a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x2a90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a95  endfinally
0x2a96  ldloc.1
0x2a97  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x2a9c  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x2aa1  ldloc.1
0x2aa2  callvirt instance object [System.Data]System.Data.Common.DbCommand::ExecuteScalar()
0x2aa7  unbox.any mvar<u1>
0x2aac  stloc.s  4
0x2aae  leave.s  loc_2ADD
0x2ab0  ldloc.1
0x2ab1  brfalse.s loc_2AB9
0x2ab3  ldloc.1
0x2ab4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ab9  endfinally
0x2aba  ldloc.0
0x2abb  brfalse.s loc_2AC3
0x2abd  ldloc.0
0x2abe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ac3  endfinally
0x2ac4  stloc.s  5
0x2ac6  ldstr    aErrorExecuting// "Error executing SQL command. Details:{0"...
0x2acb  ldc.i4.1
0x2acc  newarr   [mscorlib]System.Object
0x2ad1  dup
0x2ad2  ldc.i4.0
0x2ad3  ldloc.s  5
0x2ad5  stelem.ref
0x2ad6  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x2adb  rethrow
0x2add  ldloc.s  4
0x2adf  ret
```
