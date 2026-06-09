# Microsoft.ReportingServices.Library.DBInterface::CreateNewSnapshotVersion

- ea: `0x7c00`
- end: `0x7cc7`
- name: `Microsoft.ReportingServices.Library.DBInterface::CreateNewSnapshotVersion`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5fe10`

## callees

- `0x7c00`
- `0x7ea0`
- `0x637b0`
- `0x637c0`

## string_xrefs

- `0x7c1a`: `Attempt to mix permanent and non-permanent snapshots`
- `0x7c26`: `CreateNewSnapshotVersion`

## pseudocode

```c

```

## disassembly

```asm
0x7c00  ldarg.1
0x7c01  call     void Microsoft.ReportingServices.Library.DBInterface::ThrowOnInvalidReportSnapshot(class Microsoft.ReportingServices.Library.ReportSnapshot snapshot)
0x7c06  ldarg.2
0x7c07  call     void Microsoft.ReportingServices.Library.DBInterface::ThrowOnInvalidReportSnapshot(class Microsoft.ReportingServices.Library.ReportSnapshot snapshot)
0x7c0c  ldarg.1
0x7c0d  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7c12  ldarg.2
0x7c13  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7c18  beq.s    loc_7C25
0x7c1a  ldstr    aAttemptToMixPe// "Attempt to mix permanent and non-perman"...
0x7c1f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x7c24  throw
0x7c25  ldarg.0
0x7c26  ldstr    aCreatenewsnaps// "CreateNewSnapshotVersion"
0x7c2b  ldnull
0x7c2c  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x7c31  stloc.0
0x7c32  ldloc.0
0x7c33  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7c38  ldstr    aOldsnapshotid// "@OldSnapshotId"
0x7c3d  ldc.i4.s 0xE
0x7c3f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7c44  ldarg.1
0x7c45  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x7c4a  box      [mscorlib]System.Guid
0x7c4f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7c54  ldloc.0
0x7c55  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7c5a  ldstr    aNewsnapshotid// "@NewSnapshotId"
0x7c5f  ldc.i4.s 0xE
0x7c61  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7c66  ldarg.2
0x7c67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x7c6c  box      [mscorlib]System.Guid
0x7c71  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7c76  ldloc.0
0x7c77  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7c7c  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x7c81  ldc.i4.2
0x7c82  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7c87  ldarg.2
0x7c88  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7c8d  box      [mscorlib]System.Boolean
0x7c92  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7c97  ldloc.0
0x7c98  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7c9d  ldstr    aMachine// "@Machine"
0x7ca2  ldc.i4.s 0xC
0x7ca4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7ca9  call     string [mscorlib]System.Environment::get_MachineName()
0x7cae  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7cb3  ldloc.0
0x7cb4  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x7cb9  pop
0x7cba  leave.s  loc_7CC6
0x7cbc  ldloc.0
0x7cbd  brfalse.s loc_7CC5
0x7cbf  ldloc.0
0x7cc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7cc5  endfinally
0x7cc6  ret
```
