# Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateTask

- ea: `0x63e0`
- end: `0x6749`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateTask`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x6950`

## callees

- `0x4e10`
- `0x5330`
- `0x6140`
- `0x61a0`
- `0x63e0`
- `0x6c00`
- `0x70e0`
- `0x72d0`
- `0x7320`
- `0x8260`

## string_xrefs

- `0x657b`: `@command`

## pseudocode

```c

```

## disassembly

```asm
0x63e0  ldarg.1
0x63e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x63e6  stloc.2
0x63e7  ldloca.s 2
0x63e9  constrained. [mscorlib]System.Guid
0x63ef  callvirt instance string [mscorlib]System.Object::ToString()
0x63f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x63f9  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x63fe  stloc.0
0x63ff  ldarg.0
0x6400  ldstr    aMsdbDboSpAddJo// "msdb.dbo.sp_add_job"
0x6405  ldnull
0x6406  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x640b  stloc.3
0x640c  ldstr    aJobName// "@job_name"
0x6411  ldc.i4.s 0xC
0x6413  ldc.i4   0x80
0x6418  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x641d  stloc.s  4
0x641f  ldloc.s  4
0x6421  ldloc.0
0x6422  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6427  ldloc.3
0x6428  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x642d  ldloc.s  4
0x642f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6434  pop
0x6435  ldstr    aDescription_0// "@description"
0x643a  ldc.i4.s 0xC
0x643c  ldc.i4   0x200
0x6441  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6446  stloc.s  4
0x6448  ldloc.s  4
0x644a  call     string Microsoft.ReportingServices.Library.RepLibRes::get_TaskComment()
0x644f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6454  ldloc.3
0x6455  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x645a  ldloc.s  4
0x645c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6461  pop
0x6462  ldstr    aCategoryId// "@category_id"
0x6467  ldc.i4.8
0x6468  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x646d  stloc.s  4
0x646f  ldloc.s  4
0x6471  ldarg.0
0x6472  call     instance int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::get_CategoryID()
0x6477  box      [mscorlib]System.Int32
0x647c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6481  ldloc.3
0x6482  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6487  ldloc.s  4
0x6489  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x648e  pop
0x648f  ldloc.3
0x6490  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x6495  pop
0x6496  ldloc.3
0x6497  ldstr    aMsdbDboSpAddJo_0// "msdb.dbo.sp_add_jobserver"
0x649c  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandText(string value)
0x64a1  ldloc.3
0x64a2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x64a7  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x64ac  ldstr    aJobName// "@job_name"
0x64b1  ldc.i4.s 0xC
0x64b3  ldc.i4   0x80
0x64b8  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x64bd  stloc.s  4
0x64bf  ldloc.s  4
0x64c1  ldloc.0
0x64c2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x64c7  ldloc.3
0x64c8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x64cd  ldloc.s  4
0x64cf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x64d4  pop
0x64d5  ldstr    aServerName// "@server_name "
0x64da  ldc.i4.s 0xC
0x64dc  ldc.i4   0x80
0x64e1  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x64e6  stloc.s  4
0x64e8  ldloc.s  4
0x64ea  ldstr    aLocal_0// "(LOCAL)"
0x64ef  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x64f4  ldloc.3
0x64f5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x64fa  ldloc.s  4
0x64fc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6501  pop
0x6502  ldloc.3
0x6503  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x6508  pop
0x6509  ldloc.3
0x650a  ldstr    aMsdbDboSpAddJo_1// "msdb.dbo.sp_add_jobstep"
0x650f  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandText(string value)
0x6514  ldloc.3
0x6515  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x651a  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x651f  ldstr    aJobName// "@job_name"
0x6524  ldc.i4.s 0xC
0x6526  ldc.i4   0x80
0x652b  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6530  stloc.s  4
0x6532  ldloc.s  4
0x6534  ldloc.0
0x6535  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x653a  ldloc.3
0x653b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6540  ldloc.s  4
0x6542  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6547  pop
0x6548  ldstr    aStepName// "@step_name"
0x654d  ldc.i4.s 0xC
0x654f  ldc.i4   0x80
0x6554  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6559  stloc.s  4
0x655b  ldloc.s  4
0x655d  ldloc.0
0x655e  ldstr    aStep1// "_step_1"
0x6563  call     string [mscorlib]System.String::Concat(string, string)
0x6568  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x656d  ldloc.3
0x656e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6573  ldloc.s  4
0x6575  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x657a  pop
0x657b  ldstr    aCommand// "@command"
0x6580  ldc.i4.s 0xC
0x6582  ldc.i4   0xC81
0x6587  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x658c  stloc.s  4
0x658e  ldloc.s  4
0x6590  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6595  ldarg.0
0x6596  call     instance string Microsoft.ReportingServices.Library.SqlAgentScheduler::get_GenerateEventCommandFormat()
0x659b  ldarg.1
0x659c  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventType()
0x65a1  ldarg.1
0x65a2  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventData()
0x65a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x65ac  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x65b1  ldloc.3
0x65b2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65b7  ldloc.s  4
0x65b9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x65be  pop
0x65bf  ldloc.3
0x65c0  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x65c5  pop
0x65c6  leave.s  loc_65D2
0x65c8  ldloc.3
0x65c9  brfalse.s loc_65D1
0x65cb  ldloc.3
0x65cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65d1  endfinally
0x65d2  ldarg.1
0x65d3  newobj   instance void Microsoft.ReportingServices.Library.SqlScheduleHelper::.ctor(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x65d8  callvirt instance class Microsoft.ReportingServices.Library.SQLScheduleSet Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSQLScheduleSet()
0x65dd  ldc.i4.0
0x65de  stloc.1
0x65df  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x65e4  stloc.s  5
0x65e6  br       loc_6725
0x65eb  ldloc.s  5
0x65ed  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x65f2  castclass Microsoft.ReportingServices.Library.SQLScheduleParameters
0x65f7  stloc.s  6
0x65f9  ldloc.1
0x65fa  ldc.i4.1
0x65fb  add
0x65fc  stloc.1
0x65fd  ldc.i4.s 0xA
0x65ff  stloc.s  7
0x6601  nop
0x6602  ldarg.0
0x6603  ldstr    aMsdbDboSpAddJo_2// "msdb.dbo.sp_add_jobschedule"
0x6608  ldnull
0x6609  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x660e  stloc.s  8
0x6610  ldstr    aJobName// "@job_name"
0x6615  ldc.i4.s 0xC
0x6617  ldc.i4   0x80
0x661c  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6621  stloc.s  9
0x6623  ldloc.s  9
0x6625  ldloc.0
0x6626  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x662b  ldloc.s  8
0x662d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6632  ldloc.s  9
0x6634  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6639  pop
0x663a  ldstr    aName_1// "@name"
0x663f  ldc.i4.s 0xC
0x6641  ldc.i4   0x80
0x6646  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x664b  stloc.s  9
0x664d  ldloc.s  9
0x664f  ldstr    aSchedule// "Schedule_"
0x6654  ldloca.s 1
0x6656  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x665b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6660  call     string [mscorlib]System.String::Concat(string, string)
0x6665  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x666a  ldloc.s  8
0x666c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6671  ldloc.s  9
0x6673  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6678  pop
0x6679  ldloc.s  6
0x667b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x6680  stloc.s  0xA
0x6682  br.s     loc_66C4
0x6684  ldloc.s  0xA
0x6686  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x668b  castclass Microsoft.ReportingServices.Library.SQLScheduleParameter
0x6690  stloc.s  0xB
0x6692  ldloc.s  0xB
0x6694  ldfld    string Microsoft.ReportingServices.Library.SQLScheduleParameter::Name
0x6699  ldloc.s  0xB
0x669b  ldfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.ReportingServices.Library.SQLScheduleParameter::Type
0x66a0  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x66a5  stloc.s  9
0x66a7  ldloc.s  9
0x66a9  ldloc.s  0xB
0x66ab  ldfld    object Microsoft.ReportingServices.Library.SQLScheduleParameter::Value
0x66b0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x66b5  ldloc.s  8
0x66b7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x66bc  ldloc.s  9
0x66be  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x66c3  pop
0x66c4  ldloc.s  0xA
0x66c6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x66cb  brtrue.s loc_6684
0x66cd  leave.s  loc_66E4
0x66cf  ldloc.s  0xA
0x66d1  isinst   [mscorlib]System.IDisposable
0x66d6  stloc.s  0xC
0x66d8  ldloc.s  0xC
0x66da  brfalse.s loc_66E3
0x66dc  ldloc.s  0xC
0x66de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66e3  endfinally
0x66e4  ldloc.s  8
0x66e6  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x66eb  pop
0x66ec  leave.s  loc_66FA
0x66ee  ldloc.s  8
0x66f0  brfalse.s loc_66F9
0x66f2  ldloc.s  8
0x66f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66f9  endfinally
0x66fa  leave.s  loc_6725
0x66fc  stloc.s  0xD
0x66fe  ldloc.s  7
0x6700  ldc.i4.0
0x6701  ble.s    loc_6723
0x6703  ldloc.s  0xD
0x6705  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x670a  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::IsRetriableSqlError(int32)
0x670f  brfalse.s loc_6723
0x6711  ldloc.s  7
0x6713  ldc.i4.1
0x6714  sub
0x6715  stloc.s  7
0x6717  ldc.i4.s 0x64
0x6719  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x671e  leave    loc_6601
0x6723  rethrow
0x6725  ldloc.s  5
0x6727  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x672c  brtrue   loc_65EB
0x6731  leave.s  loc_6748
0x6733  ldloc.s  5
0x6735  isinst   [mscorlib]System.IDisposable
0x673a  stloc.s  0xC
0x673c  ldloc.s  0xC
0x673e  brfalse.s loc_6747
0x6740  ldloc.s  0xC
0x6742  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6747  endfinally
0x6748  ret
```
