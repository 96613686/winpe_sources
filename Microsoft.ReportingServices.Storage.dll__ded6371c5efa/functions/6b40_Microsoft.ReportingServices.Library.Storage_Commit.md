# Microsoft.ReportingServices.Library.Storage::Commit

- ea: `0x6b40`
- end: `0x6b64`
- name: `Microsoft.ReportingServices.Library.Storage::Commit`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x32d0`
- `0x3710`
- `0x6b40`

## pseudocode

```c

```

## disassembly

```asm
0x6b40  ldarg.0
0x6b41  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b46  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x6b4b  stloc.0
0x6b4c  ldarg.0
0x6b4d  ldfld    class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::m_connectionManager
0x6b52  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x6b57  leave.s  loc_6B63
0x6b59  ldloc.0
0x6b5a  brfalse.s loc_6B62
0x6b5c  ldloc.0
0x6b5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b62  endfinally
0x6b63  ret
```
