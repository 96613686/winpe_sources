# Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::Dispose_0

- ea: `0x3620`
- end: `0x362e`
- name: `Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::Dispose_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x35e0`

## pseudocode

```c

```

## disassembly

```asm
0x3620  ldarg.0
0x3621  ldc.i4.1
0x3622  call     instance void Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::Dispose(bool disposing)
0x3627  ldarg.0
0x3628  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x362d  ret
```
