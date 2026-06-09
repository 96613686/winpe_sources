# Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::Dispose_0

- ea: `0x39c0`
- end: `0x39ce`
- name: `Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::Dispose_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3980`

## pseudocode

```c

```

## disassembly

```asm
0x39c0  ldarg.0
0x39c1  ldc.i4.1
0x39c2  call     instance void Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::Dispose(bool disposing)
0x39c7  ldarg.0
0x39c8  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x39cd  ret
```
