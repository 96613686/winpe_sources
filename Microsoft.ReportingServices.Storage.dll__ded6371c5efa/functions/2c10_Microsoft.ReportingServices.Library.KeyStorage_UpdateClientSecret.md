# Microsoft.ReportingServices.Library.KeyStorage::UpdateClientSecret

- ea: `0x2c10`
- end: `0x2c56`
- name: `Microsoft.ReportingServices.Library.KeyStorage::UpdateClientSecret`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2c10`
- `0x6c60`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x2c10`: `UPDATE [dbo].[ConfigurationInfo]\n                               SET [Value] = @NewValue\n                             WHERE Name = 'ClientSecret'\n	                            AND cast(Value as nvarchar(max)) = @OldValue;`

## pseudocode

```c

```

## disassembly

```asm
0x2c10  ldstr    aUpdateDboConfi// "UPDATE [dbo].[ConfigurationInfo]\r\n   "...
0x2c15  stloc.0
0x2c16  ldarg.0
0x2c17  ldloc.0
0x2c18  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x2c1d  stloc.1
0x2c1e  ldloc.1
0x2c1f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2c24  ldstr    aNewvalue// "@NewValue"
0x2c29  ldarg.2
0x2c2a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2c2f  pop
0x2c30  ldloc.1
0x2c31  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2c36  ldstr    aOldvalue// "@OldValue"
0x2c3b  ldarg.1
0x2c3c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2c41  pop
0x2c42  ldloc.1
0x2c43  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2c48  pop
0x2c49  leave.s  loc_2C55
0x2c4b  ldloc.1
0x2c4c  brfalse.s loc_2C54
0x2c4e  ldloc.1
0x2c4f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c54  endfinally
0x2c55  ret
```
