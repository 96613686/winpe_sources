# Microsoft.ManagementConsole.SnapInInstaller::Uninstall

- ea: `0x39f0`
- end: `0x39fe`
- name: `Microsoft.ManagementConsole.SnapInInstaller::Uninstall`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3a00`

## pseudocode

```c

```

## disassembly

```asm
0x39f0  ldarg.0
0x39f1  ldarg.1
0x39f2  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Uninstall(class [mscorlib]System.Collections.IDictionary)
0x39f7  ldarg.0
0x39f8  call     instance void Microsoft.ManagementConsole.SnapInInstaller::RemoveAssemblySnapInsFromRegistry()
0x39fd  ret
```
