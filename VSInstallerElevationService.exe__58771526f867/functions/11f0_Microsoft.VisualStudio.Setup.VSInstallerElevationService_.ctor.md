# Microsoft.VisualStudio.Setup.VSInstallerElevationService::.ctor

- ea: `0x11f0`
- end: `0x11fd`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xfe0`

## callees

- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x11f0  ldarg.0
0x11f1  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::.ctor()
0x11f6  ldarg.0
0x11f7  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::InitializeComponent()
0x11fc  ret
```
