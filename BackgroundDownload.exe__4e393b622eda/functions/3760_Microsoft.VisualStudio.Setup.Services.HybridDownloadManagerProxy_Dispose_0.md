# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Dispose_0

- ea: `0x3760`
- end: `0x376e`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Dispose_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3730`

## pseudocode

```c

```

## disassembly

```asm
0x3760  ldarg.0
0x3761  ldc.i4.1
0x3762  call     instance void Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Dispose(bool disposing)
0x3767  ldarg.0
0x3768  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x376d  ret
```
