# Microsoft.VisualStudio.Setup.VSInstallerElevationService::Dispose

- ea: `0x1660`
- end: `0x167e`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::Dispose`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1660`

## pseudocode

```c

```

## disassembly

```asm
0x1660  ldarg.1
0x1661  brfalse.s loc_1676
0x1663  ldarg.0
0x1664  ldfld    class [System]System.ComponentModel.IContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::components
0x1669  brfalse.s loc_1676
0x166b  ldarg.0
0x166c  ldfld    class [System]System.ComponentModel.IContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::components
0x1671  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1676  ldarg.0
0x1677  ldarg.1
0x1678  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Dispose(bool)
0x167d  ret
```
