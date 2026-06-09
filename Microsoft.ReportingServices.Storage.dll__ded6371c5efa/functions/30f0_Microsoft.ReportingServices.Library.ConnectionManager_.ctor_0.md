# Microsoft.ReportingServices.Library.ConnectionManager::.ctor_0

- ea: `0x30f0`
- end: `0x3105`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::.ctor_0`
- size: `21`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e0`
- `0xe30`
- `0x1230`
- `0x17c0`
- `0x1d70`
- `0x3b90`

## callees

- `0x3060`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldarg.0
0x30f1  call     instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x30f6  ldarg.0
0x30f7  ldarg.1
0x30f8  stfld    valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType Microsoft.ReportingServices.Library.ConnectionManager::_transactionType
0x30fd  ldarg.0
0x30fe  ldarg.2
0x30ff  stfld    valuetype [System.Data]System.Data.IsolationLevel Microsoft.ReportingServices.Library.ConnectionManager::_defaultIsolationLevel
0x3104  ret
```
