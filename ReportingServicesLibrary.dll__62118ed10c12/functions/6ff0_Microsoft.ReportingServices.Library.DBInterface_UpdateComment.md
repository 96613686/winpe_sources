# Microsoft.ReportingServices.Library.DBInterface::UpdateComment

- ea: `0x6ff0`
- end: `0x706d`
- name: `Microsoft.ReportingServices.Library.DBInterface::UpdateComment`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2e10`
- `0x2eb0`
- `0x6ff0`

## string_xrefs

- `0x6ff1`: `UpdateComment`
- `0x7025`: `@CommentID`
- `0x7056`: `Update comment affected more than 1 row.`

## pseudocode

```c

```

## disassembly

```asm
0x6ff0  ldarg.0
0x6ff1  ldstr    aUpdatecomment// "UpdateComment"
0x6ff6  ldnull
0x6ff7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x6ffc  stloc.0
0x6ffd  ldloc.0
0x6ffe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7003  ldstr    aText_0// "@Text"
0x7008  ldc.i4.s 0xC
0x700a  ldc.i4   0x800
0x700f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x7014  ldarg.1
0x7015  callvirt instance string Microsoft.ReportingServices.Library.Comment::get_Text()
0x701a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x701f  ldloc.0
0x7020  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7025  ldstr    aCommentid_0// "@CommentID"
0x702a  ldc.i4.0
0x702b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7030  ldarg.1
0x7031  callvirt instance int64 Microsoft.ReportingServices.Library.Comment::get_Id()
0x7036  box      [mscorlib]System.Int64
0x703b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7040  ldloc.0
0x7041  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x7046  stloc.1
0x7047  ldloc.1
0x7048  brfalse.s loc_7052
0x704a  ldloc.1
0x704b  ldc.i4.1
0x704c  bne.un.s loc_7056
0x704e  ldc.i4.1
0x704f  stloc.2
0x7050  leave.s  loc_706B
0x7052  ldc.i4.0
0x7053  stloc.2
0x7054  leave.s  loc_706B
0x7056  ldstr    aUpdateCommentA// "Update comment affected more than 1 row"...
0x705b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x7060  throw
0x7061  ldloc.0
0x7062  brfalse.s loc_706A
0x7064  ldloc.0
0x7065  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x706a  endfinally
0x706b  ldloc.2
0x706c  ret
```
