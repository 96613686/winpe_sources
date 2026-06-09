# Microsoft.BIServer.BIService.ProjectInstaller::Install

- ea: `0x2490`
- end: `0x249e`
- name: `Microsoft.BIServer.BIService.ProjectInstaller::Install`
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
0x2490  ldarg.0
0x2491  call     instance void Microsoft.BIServer.BIService.ProjectInstaller::Initialize()
0x2496  ldarg.0
0x2497  ldarg.1
0x2498  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x249d  ret
```
