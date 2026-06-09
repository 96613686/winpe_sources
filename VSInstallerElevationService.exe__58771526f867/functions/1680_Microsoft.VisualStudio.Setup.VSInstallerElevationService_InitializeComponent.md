# Microsoft.VisualStudio.Setup.VSInstallerElevationService::InitializeComponent

- ea: `0x1680`
- end: `0x168c`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::InitializeComponent`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11f0`

## string_xrefs

- `0x1681`: `VSInstallerElevationService`

## pseudocode

```c

```

## disassembly

```asm
0x1680  ldarg.0
0x1681  ldstr    aVsinstallerele// "VSInstallerElevationService"
0x1686  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ServiceName(string)
0x168b  ret
```
