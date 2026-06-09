# Microsoft.ReportingServices.Library.DBPoll::PollingFunction

- ea: `0xe30`
- end: `0xf58`
- name: `Microsoft.ReportingServices.Library.DBPoll::PollingFunction`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x8f10`

## callees

- `0xd20`
- `0xe30`
- `0x1100`
- `0x1110`
- `0x1120`
- `0x30f0`
- `0x3170`
- `0x3230`
- `0x32e0`
- `0x32f0`
- `0x3700`
- `0x3710`
- `0x37f0`
- `0x7120`
- `0x7270`
- `0x72a0`

## pseudocode

```c

```

## disassembly

```asm
0xe30  ldc.i4.1
0xe31  stloc.0
0xe32  ldc.i4.1
0xe33  ldc.i4   0x1000
0xe38  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel defaultIsolationLevel)
0xe3d  stloc.1
0xe3e  ldloc.1
0xe3f  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0xe44  ldarg.0
0xe45  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xe4a  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0xe4f  stloc.2
0xe50  ldc.i4.0
0xe51  stloc.3
0xe52  ldloc.2
0xe53  ldloca.s 3
0xe55  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe5a  ldarg.0
0xe5b  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xe60  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xe65  stloc.s  4
0xe67  br       loc_F1E
0xe6c  ldloc.s  4
0xe6e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe73  castclass Microsoft.ReportingServices.Library.PollWorker
0xe78  stloc.s  5
0xe7a  ldarg.0
0xe7b  ldfld    bool Microsoft.ReportingServices.Library.DBPoll::m_continuePolling
0xe80  brtrue.s loc_E87
0xe82  leave    loc_F4B
0xe87  ldloc.s  5
0xe89  callvirt instance bool Microsoft.ReportingServices.Library.PollWorker::get_Poll()
0xe8e  brfalse  loc_F1E
0xe93  ldloc.1
0xe94  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0xe99  ldloc.s  5
0xe9b  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.PollWorker::get_PollCommand()
0xea0  stloc.s  6
0xea2  ldloc.s  6
0xea4  ldloc.1
0xea5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0xeaa  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Connection(class [System.Data]System.Data.IDbConnection value)
0xeaf  ldloc.s  6
0xeb1  ldloc.1
0xeb2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0xeb7  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction value)
0xebc  ldloc.s  6
0xebe  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0xec3  stloc.s  7
0xec5  ldloc.s  5
0xec7  ldloc.s  7
0xec9  callvirt instance void Microsoft.ReportingServices.Library.PollWorker::ProcessData(class [System.Data]System.Data.IDataReader reader)
0xece  leave.s  loc_EDC
0xed0  ldloc.s  7
0xed2  brfalse.s loc_EDB
0xed4  ldloc.s  7
0xed6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xedb  endfinally
0xedc  ldloc.1
0xedd  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0xee2  leave.s  loc_EF0
0xee4  ldloc.s  6
0xee6  brfalse.s loc_EEF
0xee8  ldloc.s  6
0xeea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeef  endfinally
0xef0  leave.s  loc_F1E
0xef2  stloc.s  8
0xef4  ldloc.1
0xef5  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0xefa  ldarg.0
0xefb  ldstr    aPollingfunctio// "PollingFunction"
0xf00  ldloc.s  8
0xf02  ldarg.1
0xf03  ldind.ref
0xf04  call     instance bool Microsoft.ReportingServices.Library.DBPoll::HandleException(string methodName, class [mscorlib]System.Exception e, class [mscorlib]System.Exception lastException)
0xf09  brtrue.s loc_F0D
0xf0b  rethrow
0xf0d  ldarg.1
0xf0e  ldloc.s  8
0xf10  stind.ref
0xf11  ldc.i4.0
0xf12  stloc.0
0xf13  leave.s  loc_F1E
0xf15  pop
0xf16  ldloc.1
0xf17  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0xf1c  rethrow
0xf1e  ldloc.s  4
0xf20  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf25  brtrue   loc_E6C
0xf2a  leave.s  loc_F4B
0xf2c  ldloc.s  4
0xf2e  isinst   [mscorlib]System.IDisposable
0xf33  stloc.s  9
0xf35  ldloc.s  9
0xf37  brfalse.s loc_F40
0xf39  ldloc.s  9
0xf3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf40  endfinally
0xf41  ldloc.3
0xf42  brfalse.s loc_F4A
0xf44  ldloc.2
0xf45  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf4a  endfinally
0xf4b  ldloc.0
0xf4c  stloc.3
0xf4d  leave.s  loc_F56
0xf4f  ldloc.1
0xf50  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0xf55  endfinally
0xf56  ldloc.3
0xf57  ret
```
