# Microsoft.ReportingServices.Library.QueuePollWorker::IssueTextQuey

- ea: `0x17c0`
- end: `0x182b`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::IssueTextQuey`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1590`
- `0x1690`
- `0x1770`

## callees

- `0x10f0`
- `0x17c0`
- `0x2ff0`
- `0x30f0`
- `0x3170`
- `0x31b0`
- `0x32e0`
- `0x32f0`
- `0x70c0`
- `0x70e0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldc.i4.1
0x17c1  ldc.i4   0x1000
0x17c6  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel defaultIsolationLevel)
0x17cb  stloc.0
0x17cc  ldloc.0
0x17cd  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x17d2  ldarg.0
0x17d3  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollCatalog()
0x17d8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17dd  brtrue.s loc_17EB
0x17df  ldloc.0
0x17e0  ldarg.0
0x17e1  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollCatalog()
0x17e6  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::ChangeDatabase(string database)
0x17eb  nop
0x17ec  ldarg.1
0x17ed  ldloc.0
0x17ee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x17f3  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x17f8  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command)
0x17fd  stloc.1
0x17fe  ldloc.1
0x17ff  ldc.i4.1
0x1800  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x1805  ldloc.1
0x1806  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x180b  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x1810  ldloc.1
0x1811  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x1816  pop
0x1817  leave.s  loc_182A
0x1819  ldloc.1
0x181a  brfalse.s loc_1822
0x181c  ldloc.1
0x181d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1822  endfinally
0x1823  ldloc.0
0x1824  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x1829  endfinally
0x182a  ret
```
