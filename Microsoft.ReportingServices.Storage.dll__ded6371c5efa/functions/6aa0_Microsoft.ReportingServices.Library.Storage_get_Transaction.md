# Microsoft.ReportingServices.Library.Storage::get_Transaction

- ea: `0x6aa0`
- end: `0x6ade`
- name: `Microsoft.ReportingServices.Library.Storage::get_Transaction`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6bb0`
- `0x6c00`
- `0x6c60`

## callees

- `0x3230`
- `0x32d0`
- `0x3700`
- `0x6aa0`

## pseudocode

```c

```

## disassembly

```asm
0x6aa0  ldarg.0
0x6aa1  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6aa6  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6aab  stloc.0
0x6aac  ldarg.0
0x6aad  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6ab2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x6ab7  brtrue.s loc_6AC4
0x6ab9  ldarg.0
0x6aba  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6abf  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0x6ac4  ldarg.0
0x6ac5  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6aca  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x6acf  stloc.1
0x6ad0  leave.s  loc_6ADC
0x6ad2  ldloc.0
0x6ad3  brfalse.s loc_6ADB
0x6ad5  ldloc.0
0x6ad6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6adb  endfinally
0x6adc  ldloc.1
0x6add  ret
```
