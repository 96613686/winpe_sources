# Microsoft.ReportingServices.Library.DefinitionDbInterface::LoadForDefinitionCheck

- ea: `0x2dd80`
- end: `0x2de3b`
- name: `Microsoft.ReportingServices.Library.DefinitionDbInterface::LoadForDefinitionCheck`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2d6c0`

## callees

- `0xffb0`
- `0x2dd80`
- `0x2dfe0`

## string_xrefs

- `0x2dd99`: `@Path`
- `0x2ddbb`: `@AcquireUpdateLocks`

## pseudocode

```c

```

## disassembly

```asm
0x2dd80  ldarg.3
0x2dd81  ldnull
0x2dd82  stind.ref
0x2dd83  ldarg.s  4
0x2dd85  ldnull
0x2dd86  stind.ref
0x2dd87  ldarg.0
0x2dd88  ldstr    aLoadfordefinit// "LoadForDefinitionCheck"
0x2dd8d  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CancelableSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewCancelableStandardSqlCommand(string)
0x2dd92  stloc.0
0x2dd93  ldloc.0
0x2dd94  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2dd99  ldstr    aPath// "@Path"
0x2dd9e  ldc.i4.s 0xC
0x2dda0  ldc.i4   0x1A9
0x2dda5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x2ddaa  ldarg.1
0x2ddab  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x2ddb0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x2ddb5  ldloc.0
0x2ddb6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2ddbb  ldstr    aAcquireupdatel// "@AcquireUpdateLocks"
0x2ddc0  ldc.i4.2
0x2ddc1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x2ddc6  ldarg.2
0x2ddc7  box      [mscorlib]System.Boolean
0x2ddcc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x2ddd1  ldloc.0
0x2ddd2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2ddd7  ldstr    aAuthtype// "@AuthType"
0x2dddc  ldc.i4.8
0x2dddd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x2dde2  call     unsigned int8 Microsoft.ReportingServices.Library.WebConfigUtil::get_AuthenticationType()
0x2dde7  box      [mscorlib]System.Byte
0x2ddec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x2ddf1  ldloc.0
0x2ddf2  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x2ddf7  stloc.1
0x2ddf8  ldloc.1
0x2ddf9  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2ddfe  brtrue.s loc_2DE04
0x2de00  ldc.i4.0
0x2de01  stloc.2
0x2de02  leave.s  loc_2DE39
0x2de04  ldarg.3
0x2de05  ldarg.0
0x2de06  ldloc.1
0x2de07  ldc.i4.0
0x2de08  call     instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.DefinitionDbInterface::LoadSnapshotFromDataRecord(class [System.Data]System.Data.IDataRecord reader, int32 offset)
0x2de0d  stind.ref
0x2de0e  ldloc.1
0x2de0f  ldc.i4.2
0x2de10  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2de15  brtrue.s loc_2DE21
0x2de17  ldarg.s  4
0x2de19  ldloc.1
0x2de1a  ldc.i4.2
0x2de1b  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x2de20  stind.ref
0x2de21  ldc.i4.1
0x2de22  stloc.2
0x2de23  leave.s  loc_2DE39
0x2de25  ldloc.1
0x2de26  brfalse.s loc_2DE2E
0x2de28  ldloc.1
0x2de29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2de2e  endfinally
0x2de2f  ldloc.0
0x2de30  brfalse.s loc_2DE38
0x2de32  ldloc.0
0x2de33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2de38  endfinally
0x2de39  ldloc.2
0x2de3a  ret
```
