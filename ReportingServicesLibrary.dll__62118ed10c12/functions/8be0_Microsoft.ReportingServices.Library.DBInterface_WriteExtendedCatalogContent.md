# Microsoft.ReportingServices.Library.DBInterface::WriteExtendedCatalogContent

- ea: `0x8be0`
- end: `0x8c82`
- name: `Microsoft.ReportingServices.Library.DBInterface::WriteExtendedCatalogContent`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8be0`
- `0x8db0`
- `0x8e30`

## string_xrefs

- `0x8bff`: `InitializeCatalogExtendedContentWrite`
- `0x8c42`: `InitializeCatalogExtendedContentWrite could not find the entry.`
- `0x8c65`: `Update content for catalog item with extended content`

## pseudocode

```c

```

## disassembly

```asm
0x8be0  ldarga.s 2
0x8be2  constrained. Microsoft.ReportingServices.Library.ExtendedContentType
0x8be8  callvirt instance string [mscorlib]System.Object::ToString()
0x8bed  stloc.0
0x8bee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8bf3  ldc.i4.4
0x8bf4  ldstr    aInitializeCont// "Initialize content for catalog item wit"...
0x8bf9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8bfe  ldarg.0
0x8bff  ldstr    aInitializecata// "InitializeCatalogExtendedContentWrite"
0x8c04  ldnull
0x8c05  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8c0a  stloc.2
0x8c0b  ldloc.2
0x8c0c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8c11  ldstr    aCatalogitemid// "@CatalogItemID"
0x8c16  ldarg.1
0x8c17  box      [mscorlib]System.Guid
0x8c1c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8c21  pop
0x8c22  ldloc.2
0x8c23  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8c28  ldstr    aContenttype// "@ContentType"
0x8c2d  ldloc.0
0x8c2e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8c33  pop
0x8c34  ldloc.2
0x8c35  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x8c3a  dup
0x8c3b  isinst   [mscorlib]System.DBNull
0x8c40  brfalse.s loc_8C4D
0x8c42  ldstr    aInitializecata_0// "InitializeCatalogExtendedContentWrite c"...
0x8c47  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8c4c  throw
0x8c4d  unbox.any [mscorlib]System.Int64
0x8c52  stloc.1
0x8c53  leave.s  loc_8C5F
0x8c55  ldloc.2
0x8c56  brfalse.s loc_8C5E
0x8c58  ldloc.2
0x8c59  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c5e  endfinally
0x8c5f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8c64  ldc.i4.4
0x8c65  ldstr    aUpdateContentF// "Update content for catalog item with ex"...
0x8c6a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8c6f  ldarg.0
0x8c70  ldloc.1
0x8c71  ldarg.3
0x8c72  call     instance int64 Microsoft.ReportingServices.Library.DBInterface::WriteCatalogExtendedContentById(int64 Id, class [mscorlib]System.IO.Stream stream)
0x8c77  ldarg.0
0x8c78  ldarg.1
0x8c79  ldarg.2
0x8c7a  ldarg.s  4
0x8c7c  call     instance void Microsoft.ReportingServices.Library.DBInterface::UpdateLastModifieDate(valuetype [mscorlib]System.Guid catalogItemId, valuetype Microsoft.ReportingServices.Library.ExtendedContentType extendedContentType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> modifiedDate)
0x8c81  ret
```
