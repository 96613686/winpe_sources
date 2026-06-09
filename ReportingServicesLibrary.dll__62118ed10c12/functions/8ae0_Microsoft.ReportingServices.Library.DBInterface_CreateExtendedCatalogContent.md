# Microsoft.ReportingServices.Library.DBInterface::CreateExtendedCatalogContent

- ea: `0x8ae0`
- end: `0x8b68`
- name: `Microsoft.ReportingServices.Library.DBInterface::CreateExtendedCatalogContent`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ae0`
- `0x8e30`

## string_xrefs

- `0x8ae9`: `Create new, empty extended content record`
- `0x8af4`: `InitializeCatalogExtendedContentWrite`
- `0x8b52`: `Write content into the new extended content record`

## pseudocode

```c

```

## disassembly

```asm
0x8ae0  ldc.i4.m1
0x8ae1  conv.i8
0x8ae2  stloc.0
0x8ae3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8ae8  ldc.i4.4
0x8ae9  ldstr    aCreateNewEmpty// "Create new, empty extended content reco"...
0x8aee  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8af3  ldarg.0
0x8af4  ldstr    aInitializecata// "InitializeCatalogExtendedContentWrite"
0x8af9  ldnull
0x8afa  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8aff  stloc.1
0x8b00  ldloc.1
0x8b01  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8b06  ldstr    aCatalogitemid// "@CatalogItemID"
0x8b0b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8b10  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8b15  pop
0x8b16  ldloc.1
0x8b17  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8b1c  ldstr    aContenttype// "@ContentType"
0x8b21  ldarga.s 1
0x8b23  constrained. Microsoft.ReportingServices.Library.ExtendedContentType
0x8b29  callvirt instance string [mscorlib]System.Object::ToString()
0x8b2e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8b33  pop
0x8b34  ldloc.1
0x8b35  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x8b3a  unbox.any [mscorlib]System.Int64
0x8b3f  stloc.0
0x8b40  leave.s  loc_8B4C
0x8b42  ldloc.1
0x8b43  brfalse.s loc_8B4B
0x8b45  ldloc.1
0x8b46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b4b  endfinally
0x8b4c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8b51  ldc.i4.4
0x8b52  ldstr    aWriteContentIn// "Write content into the new extended con"...
0x8b57  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8b5c  ldarg.3
0x8b5d  ldarg.0
0x8b5e  ldloc.0
0x8b5f  ldarg.2
0x8b60  call     instance int64 Microsoft.ReportingServices.Library.DBInterface::WriteCatalogExtendedContentById(int64 Id, class [mscorlib]System.IO.Stream stream)
0x8b65  stind.i8
0x8b66  ldloc.0
0x8b67  ret
```
