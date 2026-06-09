# Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction_0

- ea: `0x3700`
- end: `0x370d`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction_0`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe30`
- `0x2210`
- `0x6aa0`

## callees

- `0x3670`

## pseudocode

```c

```

## disassembly

```asm
0x3700  ldarg.0
0x3701  ldarg.0
0x3702  ldfld    valuetype [System.Data]System.Data.IsolationLevel Microsoft.ReportingServices.Library.ConnectionManager::_defaultIsolationLevel
0x3707  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel isoLevel)
0x370c  ret
```
