# Microsoft.ReportingServices.Library.DBInterface::FinalizeNewExtendedCatalogContent

- ea: `0x8b70`
- end: `0x8bdc`
- name: `Microsoft.ReportingServices.Library.DBInterface::FinalizeNewExtendedCatalogContent`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8b70`

## string_xrefs

- `0x8b76`: `Link new extended content record to a catalog record and update content size`
- `0x8b81`: `FinalizeTempCatalogExtendedContentWrite`
- `0x8bc4`: `FinalizeTempCatalogExtendedContentWrite could not find the entry.`

## pseudocode

```c

```

## disassembly

```asm
0x8b70  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8b75  ldc.i4.4
0x8b76  ldstr    aLinkNewExtende// "Link new extended content record to a c"...
0x8b7b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8b80  ldarg.0
0x8b81  ldstr    aFinalizetempca// "FinalizeTempCatalogExtendedContentWrite"
0x8b86  ldnull
0x8b87  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8b8c  stloc.0
0x8b8d  ldloc.0
0x8b8e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8b93  ldstr    aId// "@Id"
0x8b98  ldarg.1
0x8b99  box      [mscorlib]System.Int64
0x8b9e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8ba3  pop
0x8ba4  ldloc.0
0x8ba5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8baa  ldstr    aCatalogitemid// "@CatalogItemID"
0x8baf  ldarg.2
0x8bb0  box      [mscorlib]System.Guid
0x8bb5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8bba  pop
0x8bbb  ldloc.0
0x8bbc  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x8bc1  conv.i8
0x8bc2  brtrue.s loc_8BCF
0x8bc4  ldstr    aFinalizetempca_0// "FinalizeTempCatalogExtendedContentWrite"...
0x8bc9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8bce  throw
0x8bcf  leave.s  loc_8BDB
0x8bd1  ldloc.0
0x8bd2  brfalse.s loc_8BDA
0x8bd4  ldloc.0
0x8bd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bda  endfinally
0x8bdb  ret
```
