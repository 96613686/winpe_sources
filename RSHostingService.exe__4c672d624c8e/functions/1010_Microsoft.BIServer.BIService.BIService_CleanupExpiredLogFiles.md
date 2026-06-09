# Microsoft.BIServer.BIService.BIService::CleanupExpiredLogFiles

- ea: `0x1010`
- end: `0x1022`
- name: `Microsoft.BIServer.BIService.BIService::CleanupExpiredLogFiles`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ea0`

## callees

- `0x7a0`
- `0x8a0`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldarg.1
0x1011  callvirt instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_LogFolderPath()
0x1016  ldarg.1
0x1017  callvirt instance int32 Microsoft.BIServer.RSHostingService.RsTraceConfig::get_KeepFilesForDays()
0x101c  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFiles(string, int32)
0x1021  ret
```
