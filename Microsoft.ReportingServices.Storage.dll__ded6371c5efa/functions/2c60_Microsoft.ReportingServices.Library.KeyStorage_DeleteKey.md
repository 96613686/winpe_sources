# Microsoft.ReportingServices.Library.KeyStorage::DeleteKey

- ea: `0x2c60`
- end: `0x2c9d`
- name: `Microsoft.ReportingServices.Library.KeyStorage::DeleteKey`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2c60`
- `0x6a90`
- `0x6c00`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x2c61`: `DeleteKey`
- `0x2c78`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.0
0x2c61  ldstr    aDeletekey// "DeleteKey"
0x2c66  ldarg.0
0x2c67  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.Storage::get_UnverifiedConnection()
0x2c6c  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x2c71  stloc.0
0x2c72  ldloc.0
0x2c73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2c78  ldstr    aInstallationid_0// "InstallationID"
0x2c7d  ldarg.1
0x2c7e  box      [mscorlib]System.Guid
0x2c83  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2c88  pop
0x2c89  ldloc.0
0x2c8a  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2c8f  pop
0x2c90  leave.s  loc_2C9C
0x2c92  ldloc.0
0x2c93  brfalse.s loc_2C9B
0x2c95  ldloc.0
0x2c96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c9b  endfinally
0x2c9c  ret
```
