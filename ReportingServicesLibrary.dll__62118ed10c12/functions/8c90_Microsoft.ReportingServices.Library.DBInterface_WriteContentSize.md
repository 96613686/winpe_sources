# Microsoft.ReportingServices.Library.DBInterface::WriteContentSize

- ea: `0x8c90`
- end: `0x8cef`
- name: `Microsoft.ReportingServices.Library.DBInterface::WriteContentSize`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8c90`

## string_xrefs

- `0x8c96`: `Update content size for catalog item with extended content`
- `0x8ca1`: `UpdateCatalogContentSize`

## pseudocode

```c

```

## disassembly

```asm
0x8c90  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8c95  ldc.i4.4
0x8c96  ldstr    aUpdateContentS// "Update content size for catalog item wi"...
0x8c9b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8ca0  ldarg.0
0x8ca1  ldstr    aUpdatecatalogc// "UpdateCatalogContentSize"
0x8ca6  ldnull
0x8ca7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8cac  stloc.0
0x8cad  ldloc.0
0x8cae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8cb3  ldstr    aCatalogitemid// "@CatalogItemID"
0x8cb8  ldarg.1
0x8cb9  box      [mscorlib]System.Guid
0x8cbe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8cc3  pop
0x8cc4  ldloc.0
0x8cc5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8cca  ldstr    aContentsize// "@ContentSize"
0x8ccf  ldarg.2
0x8cd0  box      [mscorlib]System.Int64
0x8cd5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8cda  pop
0x8cdb  ldloc.0
0x8cdc  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x8ce1  pop
0x8ce2  leave.s  loc_8CEE
0x8ce4  ldloc.0
0x8ce5  brfalse.s loc_8CED
0x8ce7  ldloc.0
0x8ce8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ced  endfinally
0x8cee  ret
```
