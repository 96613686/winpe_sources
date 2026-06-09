# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationName

- ea: `0x1a5f0`
- end: `0x1a604`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationName`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a5f8`: `InstallationName`

## pseudocode

```c

```

## disassembly

```asm
0x1a5f0  ldarg.0
0x1a5f1  ldarg.0
0x1a5f2  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::installationName
0x1a5f7  ldarg.1
0x1a5f8  ldstr    aInstallationna// "InstallationName"
0x1a5fd  ldnull
0x1a5fe  call     T0x2B0000C9
0x1a603  ret
```
