# Microsoft.ReportingServices.Library.KeyStorage::UpdatePowerBIInformation

- ea: `0x2ba0`
- end: `0x2be0`
- name: `Microsoft.ReportingServices.Library.KeyStorage::UpdatePowerBIInformation`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2ba0`
- `0x6c60`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x2ba0`: `DELETE FROM ConfigurationInfo\n                                where [NAME] IN ('RedirectUrls');`
- `0x2ba6`: `INSERT INTO ConfigurationInfo (ConfigInfoID, Name, Value)\n                                VALUES (newid(), 'RedirectUrls', @redirectUrlsValue);`

## pseudocode

```c

```

## disassembly

```asm
0x2ba0  ldstr    aDeleteFromConf// "DELETE FROM ConfigurationInfo\r\n      "...
0x2ba5  stloc.0
0x2ba6  ldstr    aInsertIntoConf_0// "INSERT INTO ConfigurationInfo (ConfigIn"...
0x2bab  stloc.1
0x2bac  ldarg.0
0x2bad  ldloc.0
0x2bae  ldloc.1
0x2baf  call     string [mscorlib]System.String::Concat(string, string)
0x2bb4  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x2bb9  stloc.2
0x2bba  ldloc.2
0x2bbb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2bc0  ldstr    aRedirecturlsva// "@redirectUrlsValue"
0x2bc5  ldarg.1
0x2bc6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2bcb  pop
0x2bcc  ldloc.2
0x2bcd  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2bd2  pop
0x2bd3  leave.s  loc_2BDF
0x2bd5  ldloc.2
0x2bd6  brfalse.s loc_2BDE
0x2bd8  ldloc.2
0x2bd9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bde  endfinally
0x2bdf  ret
```
