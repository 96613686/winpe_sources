# Microsoft.ReportingServices.Library.ActivationDB::SetReencryptedUserServiceToken

- ea: `0x2450`
- end: `0x2494`
- name: `Microsoft.ReportingServices.Library.ActivationDB::SetReencryptedUserServiceToken`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400`

## callees

- `0x2450`

## string_xrefs

- `0x2451`: `SetReencryptedUserServiceToken`
- `0x2472`: `@ServiceToken`

## pseudocode

```c

```

## disassembly

```asm
0x2450  ldarg.0
0x2451  ldstr    aSetreencrypted_2// "SetReencryptedUserServiceToken"
0x2456  ldnull
0x2457  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x245c  stloc.0
0x245d  ldloc.0
0x245e  ldstr    aUserid// "@UserID"
0x2463  ldc.i4.s 0xE
0x2465  ldarg.1
0x2466  box      [mscorlib]System.Guid
0x246b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x2470  pop
0x2471  ldloc.0
0x2472  ldstr    aServicetoken// "@ServiceToken"
0x2477  ldc.i4.s 0xB
0x2479  ldarg.2
0x247a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x247f  pop
0x2480  ldloc.0
0x2481  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2486  pop
0x2487  leave.s  loc_2493
0x2489  ldloc.0
0x248a  brfalse.s loc_2492
0x248c  ldloc.0
0x248d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2492  endfinally
0x2493  ret
```
