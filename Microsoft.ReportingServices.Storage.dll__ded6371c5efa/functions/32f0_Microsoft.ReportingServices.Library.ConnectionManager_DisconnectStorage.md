# Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage

- ea: `0x32f0`
- end: `0x335a`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage`
- size: `106`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x1230`
- `0x17c0`
- `0x1d70`
- `0x2270`
- `0x3140`
- `0x3a40`
- `0x3ac0`
- `0x6ae0`
- `0x6b70`

## callees

- `0x32d0`
- `0x32f0`
- `0x6dd0`

## pseudocode

```c

```

## disassembly

```asm
0x32f0  ldarg.0
0x32f1  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x32f6  stloc.0
0x32f7  ldarg.0
0x32f8  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x32fd  brfalse.s loc_3329
0x32ff  ldarg.0
0x3300  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x3305  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x330a  leave.s  loc_3313
0x330c  call     void Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes(class [mscorlib]System.Exception e)
0x3311  rethrow
0x3313  ldarg.0
0x3314  ldfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_connectionWasOpened
0x3319  brfalse.s loc_3322
0x331b  ldarg.0
0x331c  ldc.i4.0
0x331d  stfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_connectionWasOpened
0x3322  ldarg.0
0x3323  ldnull
0x3324  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.ConnectionManager::_connection
0x3329  leave.s  loc_3335
0x332b  ldloc.0
0x332c  brfalse.s loc_3334
0x332e  ldloc.0
0x332f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3334  endfinally
0x3335  leave.s  loc_3359
0x3337  stloc.1
0x3338  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x333d  ldc.i4.1
0x333e  ldstr    aConnectionClos// "Connection close failed. Exception thro"...
0x3343  ldc.i4.1
0x3344  newarr   [mscorlib]System.Object
0x3349  dup
0x334a  ldc.i4.0
0x334b  ldloc.1
0x334c  callvirt instance string [mscorlib]System.Object::ToString()
0x3351  stelem.ref
0x3352  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3357  rethrow
0x3359  ret
```
