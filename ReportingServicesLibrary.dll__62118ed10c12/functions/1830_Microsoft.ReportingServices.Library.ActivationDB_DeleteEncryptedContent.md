# Microsoft.ReportingServices.Library.ActivationDB::DeleteEncryptedContent

- ea: `0x1830`
- end: `0x18ba`
- name: `Microsoft.ReportingServices.Library.ActivationDB::DeleteEncryptedContent`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xca0`

## callees

- `0x1830`
- `0x18c0`
- `0x1b00`
- `0x1bc0`
- `0x1fd0`

## string_xrefs

- `0x1831`: `DeleteEncryptedContent`
- `0x1850`: `@ConfigNamesToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x1830  ldarg.0
0x1831  ldstr    aDeleteencrypte// "DeleteEncryptedContent"
0x1836  ldarg.0
0x1837  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_UnverifiedConnection()
0x183c  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x1841  stloc.1
0x1842  ldarg.0
0x1843  ldarg.0
0x1844  ldfld    string[] Microsoft.ReportingServices.Library.ActivationDB::encryptedConfigSettingsToDelete
0x1849  call     instance class [System.Data]System.Data.DataTable Microsoft.ReportingServices.Library.ActivationDB::CreateConfigParameterList(string[] configSettings)
0x184e  stloc.2
0x184f  ldloc.1
0x1850  ldstr    aConfignamestod// "@ConfigNamesToDelete"
0x1855  ldc.i4.s 0x1E
0x1857  ldloc.2
0x1858  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x185d  pop
0x185e  ldloc.1
0x185f  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x1864  pop
0x1865  leave.s  loc_1871
0x1867  ldloc.1
0x1868  brfalse.s loc_1870
0x186a  ldloc.1
0x186b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1870  endfinally
0x1871  ldc.i4.s 0x32
0x1873  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor(int32)
0x1878  stloc.0
0x1879  ldarg.0
0x187a  ldloc.0
0x187b  call     instance void Microsoft.ReportingServices.Library.ActivationDB::ListSubscriptionIDs(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> subscriptionList)
0x1880  ldloc.0
0x1881  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1886  stloc.3
0x1887  br.s     loc_189A
0x1889  ldloca.s 3
0x188b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x1890  stloc.s  4
0x1892  ldarg.0
0x1893  ldloc.s  4
0x1895  call     instance void Microsoft.ReportingServices.Library.ActivationDB::DeleteSubscriptionEncryptedContent(valuetype [mscorlib]System.Guid subscriptionID)
0x189a  ldloca.s 3
0x189c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x18a1  brtrue.s loc_1889
0x18a3  leave.s  loc_18B3
0x18a5  ldloca.s 3
0x18a7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x18ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b2  endfinally
0x18b3  ldarg.0
0x18b4  call     instance void Microsoft.ReportingServices.Library.ActivationDB::ClearEncryptedKPIRecords()
0x18b9  ret
```
