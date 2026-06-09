# Microsoft.ReportingServices.Library.Reencryptor::UpdateKPIRecord

- ea: `0x11d0`
- end: `0x1241`
- name: `Microsoft.ReportingServices.Library.Reencryptor::UpdateKPIRecord`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xff0`

## callees

- `0x11d0`

## string_xrefs

- `0x11d2`: `UPDATE [Catalog] SET [Property] = @value WHERE [ItemID] = @key`
- `0x1224`: `Reencryption (KPI): Update Operation failed - Error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x11d0  ldc.i4.m1
0x11d1  stloc.0
0x11d2  ldstr    aUpdateCatalogS// "UPDATE [Catalog] SET [Property] = @valu"...
0x11d7  stloc.1
0x11d8  ldarg.0
0x11d9  ldfld    class Microsoft.ReportingServices.Library.ActivationDB Microsoft.ReportingServices.Library.Reencryptor::m_database
0x11de  ldloc.1
0x11df  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string)
0x11e4  stloc.2
0x11e5  ldloc.2
0x11e6  ldstr    aKey// "@key"
0x11eb  ldc.i4.s 0xE
0x11ed  ldarg.1
0x11ee  box      [mscorlib]System.Guid
0x11f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x11f8  pop
0x11f9  ldloc.2
0x11fa  ldstr    aValue_0// "@value"
0x11ff  ldc.i4.s 0xB
0x1201  ldarg.2
0x1202  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x1207  pop
0x1208  ldloc.2
0x1209  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x120e  stloc.0
0x120f  leave.s  loc_121B
0x1211  ldloc.2
0x1212  brfalse.s loc_121A
0x1214  ldloc.2
0x1215  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x121a  endfinally
0x121b  leave.s  loc_123F
0x121d  stloc.3
0x121e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1223  ldc.i4.1
0x1224  ldstr    aReencryptionKp_0// "Reencryption (KPI): Update Operation fa"...
0x1229  ldc.i4.1
0x122a  newarr   [mscorlib]System.Object
0x122f  dup
0x1230  ldc.i4.0
0x1231  ldloc.3
0x1232  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1237  stelem.ref
0x1238  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x123d  leave.s  loc_123F
0x123f  ldloc.0
0x1240  ret
```
