# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationVersion

- ea: `0x1a7a0`
- end: `0x1a7b4`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationVersion`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a7a8`: `InstallationVersion`

## pseudocode

```c

```

## disassembly

```asm
0x1a7a0  ldarg.0
0x1a7a1  ldarg.0
0x1a7a2  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::installationVersion
0x1a7a7  ldarg.1
0x1a7a8  ldstr    aInstallationve// "InstallationVersion"
0x1a7ad  ldnull
0x1a7ae  call     T0x2B0000C9
0x1a7b3  ret
```
