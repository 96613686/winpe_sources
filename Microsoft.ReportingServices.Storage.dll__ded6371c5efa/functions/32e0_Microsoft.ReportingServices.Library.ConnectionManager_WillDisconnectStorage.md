# Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage

- ea: `0x32e0`
- end: `0x32e8`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage`
- size: `8`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0xe30`
- `0x1230`
- `0x17c0`
- `0x1d70`
- `0x21c0`
- `0x3140`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  ldc.i4.1
0x32e2  stfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_willDisconnectStorage
0x32e7  ret
```
