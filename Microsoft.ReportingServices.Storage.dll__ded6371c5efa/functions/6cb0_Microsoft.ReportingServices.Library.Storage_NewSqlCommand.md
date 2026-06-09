# Microsoft.ReportingServices.Library.Storage::NewSqlCommand

- ea: `0x6cb0`
- end: `0x6cce`
- name: `Microsoft.ReportingServices.Library.Storage::NewSqlCommand`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x70d0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x6cb0  ldarg.0
0x6cb1  ldarg.2
0x6cb2  ldarg.3
0x6cb3  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x6cb8  ldnull
0x6cb9  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command, class [mscorlib]System.IDisposable connectionLockContext)
0x6cbe  dup
0x6cbf  ldarg.1
0x6cc0  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x6cc5  dup
0x6cc6  ldarg.s  4
0x6cc8  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x6ccd  ret
```
