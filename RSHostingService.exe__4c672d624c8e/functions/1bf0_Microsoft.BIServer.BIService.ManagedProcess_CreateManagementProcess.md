# Microsoft.BIServer.BIService.ManagedProcess::CreateManagementProcess

- ea: `0x1bf0`
- end: `0x1bfe`
- name: `Microsoft.BIServer.BIService.ManagedProcess::CreateManagementProcess`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## callees

- `0x1c10`
- `0x2c90`

## pseudocode

```c

```

## disassembly

```asm
0x1bf0  ldarg.0
0x1bf1  ldarg.0
0x1bf2  call     class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher Microsoft.BIServer.BIService.ProcessLaunchers.LauncherFactory::Get(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x1bf7  ldc.i4.1
0x1bf8  newobj   instance void Microsoft.BIServer.BIService.ManagedProcess::.ctor(class Microsoft.BIServer.BIService.ProcessConfig processConfig, class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher launcher, bool isManagementProcess)
0x1bfd  ret
```
