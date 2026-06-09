# Microsoft.ReportingServices.Library.SubscriptionDB::UpdateSubscriptionResult

- ea: `0x528e0`
- end: `0x5293d`
- name: `Microsoft.ReportingServices.Library.SubscriptionDB::UpdateSubscriptionResult`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x11e30`

## callees

- `0x528e0`
- `0x70f40`

## string_xrefs

- `0x52905`: `@ExtensionSettings`
- `0x528e1`: `UpdateSubscriptionResult`

## pseudocode

```c

```

## disassembly

```asm
0x528e0  ldarg.0
0x528e1  ldstr    aUpdatesubscrip_1// "UpdateSubscriptionResult"
0x528e6  ldnull
0x528e7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x528ec  stloc.0
0x528ed  ldloc.0
0x528ee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x528f3  ldstr    aSubscriptionid// "@SubscriptionID"
0x528f8  ldarg.1
0x528f9  box      [mscorlib]System.Guid
0x528fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52903  pop
0x52904  ldloc.0
0x52905  ldstr    aExtensionsetti// "@ExtensionSettings"
0x5290a  ldc.i4.s 0xB
0x5290c  ldarg.2
0x5290d  stloc.1
0x5290e  ldloc.1
0x5290f  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x52914  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52919  pop
0x5291a  ldloc.0
0x5291b  ldstr    aSubscriptionre// "@SubscriptionResult"
0x52920  ldc.i4.s 0xC
0x52922  ldarg.3
0x52923  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52928  pop
0x52929  ldloc.0
0x5292a  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x5292f  pop
0x52930  leave.s  loc_5293C
0x52932  ldloc.0
0x52933  brfalse.s loc_5293B
0x52935  ldloc.0
0x52936  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5293b  endfinally
0x5293c  ret
```
