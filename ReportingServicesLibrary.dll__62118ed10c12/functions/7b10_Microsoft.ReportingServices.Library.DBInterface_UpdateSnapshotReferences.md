# Microsoft.ReportingServices.Library.DBInterface::UpdateSnapshotReferences

- ea: `0x7b10`
- end: `0x7c00`
- name: `Microsoft.ReportingServices.Library.DBInterface::UpdateSnapshotReferences`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5fea0`

## callees

- `0x7b10`
- `0x7ea0`
- `0x637b0`
- `0x637c0`

## string_xrefs

- `0x7b2a`: `Attempt to mix permanent and non-permanent snapshots`
- `0x7b3d`: `UpdateSnapshotReferences`
- `0x7bcb`: `@UpdatedReferences`

## pseudocode

```c

```

## disassembly

```asm
0x7b10  ldarg.1
0x7b11  call     void Microsoft.ReportingServices.Library.DBInterface::ThrowOnInvalidReportSnapshot(class Microsoft.ReportingServices.Library.ReportSnapshot snapshot)
0x7b16  ldarg.2
0x7b17  call     void Microsoft.ReportingServices.Library.DBInterface::ThrowOnInvalidReportSnapshot(class Microsoft.ReportingServices.Library.ReportSnapshot snapshot)
0x7b1c  ldarg.1
0x7b1d  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7b22  ldarg.2
0x7b23  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7b28  beq.s    loc_7B35
0x7b2a  ldstr    aAttemptToMixPe// "Attempt to mix permanent and non-perman"...
0x7b2f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x7b34  throw
0x7b35  ldarg.1
0x7b36  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x7b3b  stloc.0
0x7b3c  ldarg.0
0x7b3d  ldstr    aUpdatesnapshot_0// "UpdateSnapshotReferences"
0x7b42  ldnull
0x7b43  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x7b48  stloc.1
0x7b49  ldloc.1
0x7b4a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7b4f  ldstr    aOldsnapshotid// "@OldSnapshotId"
0x7b54  ldc.i4.s 0xE
0x7b56  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7b5b  ldarg.1
0x7b5c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x7b61  box      [mscorlib]System.Guid
0x7b66  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7b6b  ldloc.1
0x7b6c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7b71  ldstr    aNewsnapshotid// "@NewSnapshotId"
0x7b76  ldc.i4.s 0xE
0x7b78  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7b7d  ldarg.2
0x7b7e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x7b83  box      [mscorlib]System.Guid
0x7b88  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7b8d  ldloc.1
0x7b8e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7b93  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x7b98  ldc.i4.2
0x7b99  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7b9e  ldloc.0
0x7b9f  box      [mscorlib]System.Boolean
0x7ba4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7ba9  ldloc.1
0x7baa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7baf  ldstr    aTransientrefco// "@TransientRefCountModifier"
0x7bb4  ldc.i4.8
0x7bb5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7bba  ldarg.3
0x7bbb  box      [mscorlib]System.Int32
0x7bc0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7bc5  ldloc.1
0x7bc6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7bcb  ldstr    aUpdatedreferen// "@UpdatedReferences"
0x7bd0  ldc.i4.8
0x7bd1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7bd6  stloc.2
0x7bd7  ldloc.2
0x7bd8  ldc.i4.2
0x7bd9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x7bde  ldloc.1
0x7bdf  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x7be4  pop
0x7be5  ldarg.s  4
0x7be7  ldloc.2
0x7be8  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x7bed  unbox.any [mscorlib]System.Int32
0x7bf2  stind.i4
0x7bf3  leave.s  loc_7BFF
0x7bf5  ldloc.1
0x7bf6  brfalse.s loc_7BFE
0x7bf8  ldloc.1
0x7bf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7bfe  endfinally
0x7bff  ret
```
