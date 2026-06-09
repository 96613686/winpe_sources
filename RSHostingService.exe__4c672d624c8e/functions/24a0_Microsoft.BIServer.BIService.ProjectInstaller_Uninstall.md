# Microsoft.BIServer.BIService.ProjectInstaller::Uninstall

- ea: `0x24a0`
- end: `0x24ae`
- name: `Microsoft.BIServer.BIService.ProjectInstaller::Uninstall`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x24e0`

## pseudocode

```c

```

## disassembly

```asm
0x24a0  ldarg.0
0x24a1  call     instance void Microsoft.BIServer.BIService.ProjectInstaller::Initialize()
0x24a6  ldarg.0
0x24a7  ldarg.1
0x24a8  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Uninstall(class [mscorlib]System.Collections.IDictionary)
0x24ad  ret
```
