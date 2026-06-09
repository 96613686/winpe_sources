# Microsoft.BIServer.BIService.ProjectInstaller::.ctor

- ea: `0x2480`
- end: `0x248d`
- name: `Microsoft.BIServer.BIService.ProjectInstaller::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x24d0`

## pseudocode

```c

```

## disassembly

```asm
0x2480  ldarg.0
0x2481  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::.ctor()
0x2486  ldarg.0
0x2487  call     instance void Microsoft.BIServer.BIService.ProjectInstaller::InitializeComponent()
0x248c  ret
```
