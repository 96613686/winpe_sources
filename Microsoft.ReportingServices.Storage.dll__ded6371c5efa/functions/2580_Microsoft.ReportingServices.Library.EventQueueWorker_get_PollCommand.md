# Microsoft.ReportingServices.Library.EventQueueWorker::get_PollCommand

- ea: `0x2580`
- end: `0x25af`
- name: `Microsoft.ReportingServices.Library.EventQueueWorker::get_PollCommand`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x19b0`
- `0x70c0`
- `0x7310`
- `0x7360`

## pseudocode

```c

```

## disassembly

```asm
0x2580  ldstr    aPolleventsforr// "PollEventsForRSProcess"
0x2585  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string)
0x258a  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command)
0x258f  dup
0x2590  ldc.i4.4
0x2591  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x2596  dup
0x2597  ldstr    aNumberofevents// "@NumberOfEvents"
0x259c  ldc.i4.8
0x259d  ldarg.0
0x259e  call     instance int32 Microsoft.ReportingServices.Library.QueuePollWorker::get_NumberOfItemsToRetrieve()
0x25a3  box      [mscorlib]System.Int32
0x25a8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string paramName, valuetype [System.Data]System.Data.SqlDbType type, object val)
0x25ad  pop
0x25ae  ret
```
