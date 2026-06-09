# Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout

- ea: `0x6ba0`
- end: `0x6ba6`
- name: `Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6bb0`
- `0x6c00`
- `0x6c60`

## callees

- `0x2ff0`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x6ba5  ret
```
