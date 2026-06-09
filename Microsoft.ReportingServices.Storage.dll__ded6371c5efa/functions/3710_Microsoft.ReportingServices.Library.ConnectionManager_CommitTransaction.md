# Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction

- ea: `0x3710`
- end: `0x37e9`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction`
- size: `217`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x2240`
- `0x3420`
- `0x34c0`
- `0x3ac0`
- `0x6b40`

## callees

- `0x32d0`
- `0x3710`
- `0x3a80`
- `0x6dd0`

## string_xrefs

- `0x376e`: `Transaction commit.`
- `0x3781`: `Transaction commit failed. Exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3710  ldarg.0
0x3711  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x3716  stloc.0
0x3717  ldarg.0
0x3718  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::CheckForSingleCommit()
0x371d  ldarg.0
0x371e  ldfld    valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::_transactionType
0x3723  ldc.i4.1
0x3724  bne.un.s loc_372B
0x3726  leave    loc_37E8
0x372b  ldarg.0
0x372c  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3731  brfalse  loc_37DC
0x3736  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x373b  stloc.1
0x373c  ldarg.0
0x373d  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3742  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x3747  leave.s  loc_3750
0x3749  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x374e  rethrow
0x3750  leave.s  loc_375C
0x3752  ldloc.1
0x3753  brfalse.s loc_375B
0x3755  ldloc.1
0x3756  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x375b  endfinally
0x375c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3761  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x3766  brfalse.s loc_3778
0x3768  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x376d  ldc.i4.4
0x376e  ldstr    aTransactionCom// "Transaction commit."
0x3773  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3778  leave.s  loc_37E8
0x377a  stloc.2
0x377b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3780  ldc.i4.1
0x3781  ldstr    aTransactionCom_0// "Transaction commit failed. Exception th"...
0x3786  ldc.i4.1
0x3787  newarr   [mscorlib]System.Object
0x378c  dup
0x378d  ldc.i4.0
0x378e  ldloc.2
0x378f  callvirt instance string [mscorlib]System.Object::ToString()
0x3794  stelem.ref
0x3795  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x379a  rethrow
0x379c  nop
0x379d  ldarg.0
0x379e  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x37a3  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Dispose()
0x37a8  leave.s  loc_37DB
0x37aa  stloc.3
0x37ab  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x37b0  ldc.i4.1
0x37b1  ldstr    aTransactionDis// "Transaction dispose failed. Exception t"...
0x37b6  ldc.i4.1
0x37b7  newarr   [mscorlib]System.Object
0x37bc  dup
0x37bd  ldc.i4.0
0x37be  ldloc.3
0x37bf  callvirt instance string [mscorlib]System.Object::ToString()
0x37c4  stelem.ref
0x37c5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x37ca  leave.s  loc_37DB
0x37cc  ldarg.0
0x37cd  ldnull
0x37ce  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x37d3  ldarg.0
0x37d4  ldc.i4.1
0x37d5  stfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_performedCommitOrRollback
0x37da  endfinally
0x37db  endfinally
0x37dc  leave.s  loc_37E8
0x37de  ldloc.0
0x37df  brfalse.s loc_37E7
0x37e1  ldloc.0
0x37e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37e7  endfinally
0x37e8  ret
```
