# Microsoft.ReportingServices.Library.Storage::AbortTransaction

- ea: `0x6b10`
- end: `0x6b34`
- name: `Microsoft.ReportingServices.Library.Storage::AbortTransaction`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x32d0`
- `0x37f0`
- `0x6b10`

## pseudocode

```c

```

## disassembly

```asm
0x6b10  ldarg.0
0x6b11  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b16  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6b1b  stloc.0
0x6b1c  ldarg.0
0x6b1d  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b22  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x6b27  leave.s  loc_6B33
0x6b29  ldloc.0
0x6b2a  brfalse.s loc_6B32
0x6b2c  ldloc.0
0x6b2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b32  endfinally
0x6b33  ret
```
