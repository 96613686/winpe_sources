# Microsoft.ManagementConsole.SnapInInstaller::Rollback

- ea: `0x39e0`
- end: `0x39ee`
- name: `Microsoft.ManagementConsole.SnapInInstaller::Rollback`
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
0x39e0  ldarg.0
0x39e1  ldarg.1
0x39e2  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Rollback(class [mscorlib]System.Collections.IDictionary)
0x39e7  ldarg.0
0x39e8  call     instance void Microsoft.ManagementConsole.SnapInInstaller::RemoveAssemblySnapInsFromRegistry()
0x39ed  ret
```
