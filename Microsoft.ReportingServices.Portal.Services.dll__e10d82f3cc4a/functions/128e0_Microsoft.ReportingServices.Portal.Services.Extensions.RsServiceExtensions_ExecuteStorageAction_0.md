# Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction_0

- ea: `0x128e0`
- end: `0x128ee`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction_0`
- size: `14`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x990`
- `0x1a00`
- `0x1ba0`
- `0x1c20`
- `0x41f0`
- `0x5ff0`
- `0x8950`
- `0x8d60`

## callees

- `0x128f0`

## pseudocode

```c

```

## disassembly

```asm
0x128e0  ldarg.0
0x128e1  ldarg.1
0x128e2  ldarg.2
0x128e3  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x128e8  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel isolationLevel)
0x128ed  ret
```
