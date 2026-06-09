# Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction

- ea: `0x128c0`
- end: `0x128d2`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction`
- size: `18`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1b50`
- `0x1c20`
- `0x34b0`
- `0x35b0`
- `0x3b00`
- `0x3da0`
- `0x3e40`
- `0x3e80`
- `0x3f70`
- `0x3ff0`
- `0x40e0`
- `0x49e0`
- `0x4b50`
- `0x5110`
- `0x52c0`
- `0x5450`
- `0x6170`
- `0x7cd0`
- `0x7d10`
- `0x7d60`
- `0xd340`

## callees

- `0x128f0`

## pseudocode

```c

```

## disassembly

```asm
0x128c0  ldarg.0
0x128c1  ldarg.1
0x128c2  call     valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultTransactionType()
0x128c7  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x128cc  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel isolationLevel)
0x128d1  ret
```
