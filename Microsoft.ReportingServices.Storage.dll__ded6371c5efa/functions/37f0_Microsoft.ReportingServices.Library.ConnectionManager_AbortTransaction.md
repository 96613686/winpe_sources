# Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction

- ea: `0x37f0`
- end: `0x3904`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xe30`
- `0x2190`
- `0x6b10`

## callees

- `0x32d0`
- `0x37f0`
- `0x3a80`
- `0x6dd0`

## string_xrefs

- `0x3888`: `Transaction rollback was not executed connection is invalid`
- `0x38a4`: `Transaction rollback.`
- `0x38dc`: `Transaction rollback failed. Exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x37f0  ldarg.0
0x37f1  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x37f6  stloc.0
0x37f7  ldarg.0
0x37f8  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::CheckForSingleCommit()
0x37fd  ldarg.0
0x37fe  ldfld    valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::_transactionType
0x3803  ldc.i4.1
0x3804  bne.un.s loc_380B
0x3806  leave    loc_3903
0x380b  ldarg.0
0x380c  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3811  brfalse  loc_38F7
0x3816  ldarg.0
0x3817  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x381c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction::get_Connection()
0x3821  brfalse.s loc_3876
0x3823  ldarg.0
0x3824  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3829  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction::get_Connection()
0x382e  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x3833  brfalse.s loc_3876
0x3835  ldarg.0
0x3836  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x383b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction::get_Connection()
0x3840  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.Common.DbConnection::get_State()
0x3845  ldc.i4.s 0x10
0x3847  beq.s    loc_3876
0x3849  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x384e  stloc.1
0x384f  ldarg.0
0x3850  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x3855  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x385a  ldarg.0
0x385b  ldc.i4.1
0x385c  stfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_performedCommitOrRollback
0x3861  leave.s  loc_386A
0x3863  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x3868  rethrow
0x386a  leave.s  loc_3892
0x386c  ldloc.1
0x386d  brfalse.s loc_3875
0x386f  ldloc.1
0x3870  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3875  endfinally
0x3876  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x387b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x3880  brfalse.s loc_3892
0x3882  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3887  ldc.i4.2
0x3888  ldstr    aTransactionRol// "Transaction rollback was not executed c"...
0x388d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x3892  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3897  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x389c  brfalse.s loc_38AE
0x389e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x38a3  ldc.i4.4
0x38a4  ldstr    aTransactionRol_0// "Transaction rollback."
0x38a9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x38ae  ldarg.0
0x38af  ldnull
0x38b0  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x38b5  leave.s  loc_3903
0x38b7  stloc.2
0x38b8  ldloc.2
0x38b9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x38be  brfalse.s loc_38D6
0x38c0  ldloc.2
0x38c1  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x38c6  ldsfld   int32 Microsoft.ReportingServices.Library.Native::SqlTransactionAbortedCode
0x38cb  bne.un.s loc_38D6
0x38cd  ldarg.0
0x38ce  ldnull
0x38cf  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x38d4  leave.s  loc_3903
0x38d6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x38db  ldc.i4.1
0x38dc  ldstr    aTransactionRol_1// "Transaction rollback failed. Exception "...
0x38e1  ldc.i4.1
0x38e2  newarr   [mscorlib]System.Object
0x38e7  dup
0x38e8  ldc.i4.0
0x38e9  ldloc.2
0x38ea  callvirt instance string [mscorlib]System.Object::ToString()
0x38ef  stelem.ref
0x38f0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x38f5  rethrow
0x38f7  leave.s  loc_3903
0x38f9  ldloc.0
0x38fa  brfalse.s loc_3902
0x38fc  ldloc.0
0x38fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3902  endfinally
0x3903  ret
```
