# Microsoft.ReportingServices.Library.ActivationDB::UpdateKPIRecord

- ea: `0x1a90`
- end: `0x1afc`
- name: `Microsoft.ReportingServices.Library.ActivationDB::UpdateKPIRecord`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18c0`

## callees

- `0x1a90`

## string_xrefs

- `0x1a92`: `UPDATE [Catalog] SET [Property] = @value WHERE [ItemID] = @key`
- `0x1adf`: `DeleteEncrypted (KPI): Update Operation failed - Error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  ldc.i4.m1
0x1a91  stloc.0
0x1a92  ldstr    aUpdateCatalogS// "UPDATE [Catalog] SET [Property] = @valu"...
0x1a97  stloc.1
0x1a98  ldarg.0
0x1a99  ldloc.1
0x1a9a  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string)
0x1a9f  stloc.2
0x1aa0  ldloc.2
0x1aa1  ldstr    aKey// "@key"
0x1aa6  ldc.i4.s 0xE
0x1aa8  ldarg.1
0x1aa9  box      [mscorlib]System.Guid
0x1aae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x1ab3  pop
0x1ab4  ldloc.2
0x1ab5  ldstr    aValue_0// "@value"
0x1aba  ldc.i4.s 0xB
0x1abc  ldarg.2
0x1abd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x1ac2  pop
0x1ac3  ldloc.2
0x1ac4  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x1ac9  stloc.0
0x1aca  leave.s  loc_1AD6
0x1acc  ldloc.2
0x1acd  brfalse.s loc_1AD5
0x1acf  ldloc.2
0x1ad0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ad5  endfinally
0x1ad6  leave.s  loc_1AFA
0x1ad8  stloc.3
0x1ad9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1ade  ldc.i4.1
0x1adf  ldstr    aDeleteencrypte_1// "DeleteEncrypted (KPI): Update Operation"...
0x1ae4  ldc.i4.1
0x1ae5  newarr   [mscorlib]System.Object
0x1aea  dup
0x1aeb  ldc.i4.0
0x1aec  ldloc.3
0x1aed  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1af2  stelem.ref
0x1af3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1af8  leave.s  loc_1AFA
0x1afa  ldloc.0
0x1afb  ret
```
