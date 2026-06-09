# Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::Dispose_0

- ea: `0x3890`
- end: `0x389e`
- name: `Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::Dispose_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3850`

## pseudocode

```c

```

## disassembly

```asm
0x3890  ldarg.0
0x3891  ldc.i4.1
0x3892  call     instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::Dispose(bool disposing)
0x3897  ldarg.0
0x3898  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x389d  ret
```
