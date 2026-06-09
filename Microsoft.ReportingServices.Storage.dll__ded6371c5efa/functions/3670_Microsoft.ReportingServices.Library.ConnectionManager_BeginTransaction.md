# Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction

- ea: `0x3670`
- end: `0x36fd`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3700`
- `0x3ac0`

## callees

- `0x3170`
- `0x32d0`
- `0x3670`
- `0x6dd0`

## string_xrefs

- `0x3690`: `Transaction is already open`

## pseudocode

```c

```

## disassembly

```asm
0x3670  ldarg.0
0x3671  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x3676  stloc.0
0x3677  ldarg.0
0x3678  ldfld    valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::_transactionType
0x367d  ldc.i4.1
0x367e  bne.un.s loc_3682
0x3680  leave.s  loc_36FC
0x3682  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3687  ldarg.0
0x3688  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x368d  ldnull
0x368e  ceq
0x3690  ldstr    aTransactionIsA// "Transaction is already open"
0x3695  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x369a  ldarg.0
0x369b  ldarg.0
0x369c  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x36a1  ldarg.1
0x36a2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel)
0x36a7  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::_Transaction
0x36ac  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x36b1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x36b6  brfalse.s loc_36C8
0x36b8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x36bd  ldc.i4.4
0x36be  ldstr    aTransactionBeg// "Transaction begin."
0x36c3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x36c8  leave.s  loc_36FC
0x36ca  stloc.1
0x36cb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x36d0  ldc.i4.1
0x36d1  ldstr    aTransactionBeg_0// "Transaction begin failed. Exception thr"...
0x36d6  ldc.i4.1
0x36d7  newarr   [mscorlib]System.Object
0x36dc  dup
0x36dd  ldc.i4.0
0x36de  ldloc.1
0x36df  callvirt instance string [mscorlib]System.Object::ToString()
0x36e4  stelem.ref
0x36e5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x36ea  ldloc.1
0x36eb  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x36f0  rethrow
0x36f2  ldloc.0
0x36f3  brfalse.s loc_36FB
0x36f5  ldloc.0
0x36f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36fb  endfinally
0x36fc  ret
```
