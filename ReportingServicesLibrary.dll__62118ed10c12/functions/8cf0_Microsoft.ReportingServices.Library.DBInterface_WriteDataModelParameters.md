# Microsoft.ReportingServices.Library.DBInterface::WriteDataModelParameters

- ea: `0x8cf0`
- end: `0x8d4a`
- name: `Microsoft.ReportingServices.Library.DBInterface::WriteDataModelParameters`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8cf0`

## string_xrefs

- `0x8cf6`: `Update parameters for catalog item`
- `0x8d01`: `UpdateDataModelParametersById`

## pseudocode

```c

```

## disassembly

```asm
0x8cf0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8cf5  ldc.i4.4
0x8cf6  ldstr    aUpdateParamete// "Update parameters for catalog item"
0x8cfb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8d00  ldarg.0
0x8d01  ldstr    aUpdatedatamode// "UpdateDataModelParametersById"
0x8d06  ldnull
0x8d07  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8d0c  stloc.0
0x8d0d  ldloc.0
0x8d0e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8d13  ldstr    aCatalogitemid// "@CatalogItemID"
0x8d18  ldarg.1
0x8d19  box      [mscorlib]System.Guid
0x8d1e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8d23  pop
0x8d24  ldloc.0
0x8d25  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8d2a  ldstr    aParameters// "@Parameters"
0x8d2f  ldarg.2
0x8d30  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8d35  pop
0x8d36  ldloc.0
0x8d37  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x8d3c  pop
0x8d3d  leave.s  loc_8D49
0x8d3f  ldloc.0
0x8d40  brfalse.s loc_8D48
0x8d42  ldloc.0
0x8d43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d48  endfinally
0x8d49  ret
```
