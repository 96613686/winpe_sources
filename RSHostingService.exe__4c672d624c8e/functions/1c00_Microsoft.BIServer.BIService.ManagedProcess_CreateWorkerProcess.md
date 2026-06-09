# Microsoft.BIServer.BIService.ManagedProcess::CreateWorkerProcess

- ea: `0x1c00`
- end: `0x1c0e`
- name: `Microsoft.BIServer.BIService.ManagedProcess::CreateWorkerProcess`
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
0x1c00  ldarg.0
0x1c01  ldarg.0
0x1c02  call     class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher Microsoft.BIServer.BIService.ProcessLaunchers.LauncherFactory::Get(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x1c07  ldc.i4.0
0x1c08  newobj   instance void Microsoft.BIServer.BIService.ManagedProcess::.ctor(class Microsoft.BIServer.BIService.ProcessConfig processConfig, class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher launcher, bool isManagementProcess)
0x1c0d  ret
```
