# Microsoft.BIServer.BIService.ProjectInstaller::Dispose

- ea: `0x24b0`
- end: `0x24ce`
- name: `Microsoft.BIServer.BIService.ProjectInstaller::Dispose`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x24b0`

## pseudocode

```c

```

## disassembly

```asm
0x24b0  ldarg.1
0x24b1  brfalse.s loc_24C6
0x24b3  ldarg.0
0x24b4  ldfld    class [System]System.ComponentModel.IContainer Microsoft.BIServer.BIService.ProjectInstaller::components
0x24b9  brfalse.s loc_24C6
0x24bb  ldarg.0
0x24bc  ldfld    class [System]System.ComponentModel.IContainer Microsoft.BIServer.BIService.ProjectInstaller::components
0x24c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24c6  ldarg.0
0x24c7  ldarg.1
0x24c8  call     instance void [System]System.ComponentModel.Component::Dispose(bool)
0x24cd  ret
```
