# Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose

- ea: `0xf20`
- end: `0xf2e`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1370`

## callees

- `0xf30`

## pseudocode

```c

```

## disassembly

```asm
0xf20  ldarg.0
0xf21  ldc.i4.1
0xf22  call     instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose(bool disposing)
0xf27  ldarg.0
0xf28  call     void [mscorlib]System.GC::SuppressFinalize(object)
0xf2d  ret
```
