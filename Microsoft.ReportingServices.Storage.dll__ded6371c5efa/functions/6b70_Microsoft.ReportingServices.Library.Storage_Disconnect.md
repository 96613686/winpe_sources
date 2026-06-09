# Microsoft.ReportingServices.Library.Storage::Disconnect

- ea: `0x6b70`
- end: `0x6b9c`
- name: `Microsoft.ReportingServices.Library.Storage::Disconnect`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x32d0`
- `0x32f0`
- `0x6b70`

## pseudocode

```c

```

## disassembly

```asm
0x6b70  ldarg.0
0x6b71  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b76  brfalse.s loc_6B9B
0x6b78  ldarg.0
0x6b79  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b7e  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6b83  stloc.0
0x6b84  ldarg.0
0x6b85  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b8a  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x6b8f  leave.s  loc_6B9B
0x6b91  ldloc.0
0x6b92  brfalse.s loc_6B9A
0x6b94  ldloc.0
0x6b95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b9a  endfinally
0x6b9b  ret
```
