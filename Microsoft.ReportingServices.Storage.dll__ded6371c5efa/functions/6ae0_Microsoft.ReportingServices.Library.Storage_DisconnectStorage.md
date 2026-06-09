# Microsoft.ReportingServices.Library.Storage::DisconnectStorage

- ea: `0x6ae0`
- end: `0x6b0c`
- name: `Microsoft.ReportingServices.Library.Storage::DisconnectStorage`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`

## callees

- `0x32d0`
- `0x32f0`
- `0x6ae0`

## pseudocode

```c

```

## disassembly

```asm
0x6ae0  ldarg.0
0x6ae1  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6ae6  brfalse.s loc_6B0B
0x6ae8  ldarg.0
0x6ae9  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6aee  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6af3  stloc.0
0x6af4  ldarg.0
0x6af5  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6afa  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x6aff  leave.s  loc_6B0B
0x6b01  ldloc.0
0x6b02  brfalse.s loc_6B0A
0x6b04  ldloc.0
0x6b05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b0a  endfinally
0x6b0b  ret
```
