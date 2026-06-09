# Microsoft.ReportingServices.DataExtensions.TransactionWrapper::Rollback

- ea: `0x3490`
- end: `0x34ec`
- name: `Microsoft.ReportingServices.DataExtensions.TransactionWrapper::Rollback`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x3490`
- `0x34f0`

## string_xrefs

- `0x34e1`: `TransactionWrapper.Rollback not called, connection is not valid`

## pseudocode

```c

```

## disassembly

```asm
0x3490  ldarg.0
0x3491  call     instance class [System.Data]System.Data.IDbTransaction Microsoft.ReportingServices.DataExtensions.TransactionWrapper::get_UnderlyingTransaction()
0x3496  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbTransaction::get_Connection()
0x349b  brfalse.s loc_34CF
0x349d  ldarg.0
0x349e  call     instance class [System.Data]System.Data.IDbTransaction Microsoft.ReportingServices.DataExtensions.TransactionWrapper::get_UnderlyingTransaction()
0x34a3  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbTransaction::get_Connection()
0x34a8  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x34ad  brfalse.s loc_34CF
0x34af  ldarg.0
0x34b0  call     instance class [System.Data]System.Data.IDbTransaction Microsoft.ReportingServices.DataExtensions.TransactionWrapper::get_UnderlyingTransaction()
0x34b5  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbTransaction::get_Connection()
0x34ba  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x34bf  ldc.i4.s 0x10
0x34c1  beq.s    loc_34CF
0x34c3  ldarg.0
0x34c4  call     instance class [System.Data]System.Data.IDbTransaction Microsoft.ReportingServices.DataExtensions.TransactionWrapper::get_UnderlyingTransaction()
0x34c9  callvirt instance void [System.Data]System.Data.IDbTransaction::Rollback()
0x34ce  ret
0x34cf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x34d4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x34d9  brfalse.s loc_34EB
0x34db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x34e0  ldc.i4.2
0x34e1  ldstr    aTransactionwra// "TransactionWrapper.Rollback not called,"...
0x34e6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x34eb  ret
```
