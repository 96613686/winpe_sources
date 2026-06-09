# Microsoft.ReportingServices.Library.Security::DeleteAllModelItemPolicies

- ea: `0x4a1c0`
- end: `0x4a1f5`
- name: `Microsoft.ReportingServices.Library.Security::DeleteAllModelItemPolicies`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30ee0`

## callees

- `0x4a1c0`

## string_xrefs

- `0x4a1ce`: `@Path`
- `0x4a1c1`: `DeleteAllModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x4a1c0  ldarg.0
0x4a1c1  ldstr    aDeleteallmodel// "DeleteAllModelItemPolicies"
0x4a1c6  ldnull
0x4a1c7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4a1cc  stloc.0
0x4a1cd  ldloc.0
0x4a1ce  ldstr    aPath// "@Path"
0x4a1d3  ldc.i4.s 0xC
0x4a1d5  ldarg.1
0x4a1d6  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4a1db  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4a1e0  pop
0x4a1e1  ldloc.0
0x4a1e2  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x4a1e7  pop
0x4a1e8  leave.s  loc_4A1F4
0x4a1ea  ldloc.0
0x4a1eb  brfalse.s loc_4A1F3
0x4a1ed  ldloc.0
0x4a1ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a1f3  endfinally
0x4a1f4  ret
```
