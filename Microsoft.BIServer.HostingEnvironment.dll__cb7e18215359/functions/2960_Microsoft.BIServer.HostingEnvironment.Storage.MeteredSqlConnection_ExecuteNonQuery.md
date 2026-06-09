# Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteNonQuery

- ea: `0x2960`
- end: `0x2a1f`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteNonQuery`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x15d0`
- `0x1be0`
- `0x2960`

## string_xrefs

- `0x2a07`: `Error executing SQL command. Details:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x2960  ldc.i4.3
0x2961  newarr   [mscorlib]System.String
0x2966  dup
0x2967  ldc.i4.0
0x2968  ldstr    aSql// "SQL"
0x296d  stelem.ref
0x296e  dup
0x296f  ldc.i4.1
0x2970  ldstr    aExec// "Exec"
0x2975  stelem.ref
0x2976  dup
0x2977  ldc.i4.2
0x2978  ldarg.1
0x2979  stelem.ref
0x297a  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x297f  stloc.0
0x2980  ldarg.1
0x2981  ldarg.0
0x2982  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x2987  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x298c  stloc.1
0x298d  ldarg.2
0x298e  brfalse.s loc_29D9
0x2990  ldarg.2
0x2991  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x2996  stloc.2
0x2997  br.s     loc_29C0
0x2999  ldloca.s 2
0x299b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x29a0  stloc.3
0x29a1  ldloc.1
0x29a2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x29a7  ldloca.s 3
0x29a9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x29ae  ldloca.s 3
0x29b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x29b5  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, object)
0x29ba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x29bf  pop
0x29c0  ldloca.s 2
0x29c2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x29c7  brtrue.s loc_2999
0x29c9  leave.s  loc_29D9
0x29cb  ldloca.s 2
0x29cd  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x29d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29d8  endfinally
0x29d9  ldloc.1
0x29da  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x29df  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x29e4  ldloc.1
0x29e5  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x29ea  pop
0x29eb  leave.s  loc_29F7
0x29ed  ldloc.1
0x29ee  brfalse.s loc_29F6
0x29f0  ldloc.1
0x29f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29f6  endfinally
0x29f7  leave.s  loc_2A03
0x29f9  ldloc.0
0x29fa  brfalse.s loc_2A02
0x29fc  ldloc.0
0x29fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a02  endfinally
0x2a03  leave.s  loc_2A1E
0x2a05  stloc.s  4
0x2a07  ldstr    aErrorExecuting// "Error executing SQL command. Details:{0"...
0x2a0c  ldc.i4.1
0x2a0d  newarr   [mscorlib]System.Object
0x2a12  dup
0x2a13  ldc.i4.0
0x2a14  ldloc.s  4
0x2a16  stelem.ref
0x2a17  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x2a1c  rethrow
0x2a1e  ret
```
