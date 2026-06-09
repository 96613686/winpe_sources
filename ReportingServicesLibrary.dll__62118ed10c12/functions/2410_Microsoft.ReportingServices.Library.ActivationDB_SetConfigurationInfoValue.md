# Microsoft.ReportingServices.Library.ActivationDB::SetConfigurationInfoValue

- ea: `0x2410`
- end: `0x244f`
- name: `Microsoft.ReportingServices.Library.ActivationDB::SetConfigurationInfoValue`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x13b0`

## callees

- `0x2410`

## string_xrefs

- `0x2411`: `SetConfigurationInfoValue`
- `0x241e`: `@ConfigValue`
- `0x242d`: `@ConfigName`

## pseudocode

```c

```

## disassembly

```asm
0x2410  ldarg.0
0x2411  ldstr    aSetconfigurati// "SetConfigurationInfoValue"
0x2416  ldnull
0x2417  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x241c  stloc.0
0x241d  ldloc.0
0x241e  ldstr    aConfigvalue// "@ConfigValue"
0x2423  ldc.i4.s 0xC
0x2425  ldarg.2
0x2426  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x242b  pop
0x242c  ldloc.0
0x242d  ldstr    aConfigname_0// "@ConfigName"
0x2432  ldc.i4.s 0xC
0x2434  ldarg.1
0x2435  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x243a  pop
0x243b  ldloc.0
0x243c  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2441  pop
0x2442  leave.s  loc_244E
0x2444  ldloc.0
0x2445  brfalse.s loc_244D
0x2447  ldloc.0
0x2448  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x244d  endfinally
0x244e  ret
```
