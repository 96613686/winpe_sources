# Microsoft.ReportingServices.Library.SqlAgentScheduler::DeleteTask

- ea: `0x68b0`
- end: `0x6943`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::DeleteTask`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6950`

## callees

- `0x68b0`
- `0x6c00`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x68b5`: `msdb.dbo.sp_delete_job`

## pseudocode

```c

```

## disassembly

```asm
0x68b0  ldc.i4.s 0xA
0x68b2  stloc.0
0x68b3  nop
0x68b4  ldarg.0
0x68b5  ldstr    aMsdbDboSpDelet// "msdb.dbo.sp_delete_job"
0x68ba  ldnull
0x68bb  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x68c0  stloc.1
0x68c1  ldstr    aJobName// "@job_name"
0x68c6  ldc.i4.s 0xC
0x68c8  ldc.i4   0x80
0x68cd  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x68d2  stloc.2
0x68d3  ldloc.2
0x68d4  ldarga.s 1
0x68d6  constrained. [mscorlib]System.Guid
0x68dc  callvirt instance string [mscorlib]System.Object::ToString()
0x68e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68e6  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x68eb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x68f0  ldloc.1
0x68f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x68f6  ldloc.2
0x68f7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x68fc  pop
0x68fd  ldloc.1
0x68fe  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x6903  pop
0x6904  leave.s  loc_6910
0x6906  ldloc.1
0x6907  brfalse.s loc_690F
0x6909  ldloc.1
0x690a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x690f  endfinally
0x6910  leave.s  loc_6942
0x6912  stloc.3
0x6913  ldloc.0
0x6914  ldc.i4.0
0x6915  ble.s    loc_6931
0x6917  ldloc.3
0x6918  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x691d  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::IsRetriableSqlError(int32)
0x6922  brfalse.s loc_6931
0x6924  ldloc.0
0x6925  ldc.i4.1
0x6926  sub
0x6927  stloc.0
0x6928  ldc.i4.s 0x64
0x692a  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x692f  leave.s  loc_68B3
0x6931  ldloc.3
0x6932  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x6937  ldc.i4   0x37B6
0x693c  beq.s    loc_6940
0x693e  rethrow
0x6940  leave.s  loc_6942
0x6942  ret
```
