# Microsoft.ReportingServices.Library.KeyStorage::SetKeysForInstallation

- ea: `0x2860`
- end: `0x28bf`
- name: `Microsoft.ReportingServices.Library.KeyStorage::SetKeysForInstallation`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3420`
- `0x34c0`

## callees

- `0x2860`
- `0x6c00`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x2861`: `SetKeysForInstallation`
- `0x2873`: `@InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldarg.0
0x2861  ldstr    aSetkeysforinst// "SetKeysForInstallation"
0x2866  ldnull
0x2867  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x286c  stloc.0
0x286d  ldloc.0
0x286e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2873  ldstr    aInstallationid// "@InstallationID"
0x2878  ldarg.1
0x2879  box      [mscorlib]System.Guid
0x287e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2883  pop
0x2884  ldarg.2
0x2885  brfalse.s loc_2899
0x2887  ldloc.0
0x2888  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x288d  ldstr    aSymmetrickey// "@SymmetricKey"
0x2892  ldarg.2
0x2893  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2898  pop
0x2899  ldloc.0
0x289a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x289f  ldstr    aPublickey// "@PublicKey"
0x28a4  ldarg.3
0x28a5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28aa  pop
0x28ab  ldloc.0
0x28ac  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x28b1  pop
0x28b2  leave.s  loc_28BE
0x28b4  ldloc.0
0x28b5  brfalse.s loc_28BD
0x28b7  ldloc.0
0x28b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28bd  endfinally
0x28be  ret
```
