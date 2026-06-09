# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstalledChannelUri

- ea: `0x1a8e0`
- end: `0x1a8f8`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstalledChannelUri`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a8e8`: `InstalledChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x1a8e0  ldarg.0
0x1a8e1  ldarg.0
0x1a8e2  ldflda   class [System]System.Uri Microsoft.VisualStudio.Setup.Cache.Instance::installedChannelUri
0x1a8e7  ldarg.1
0x1a8e8  ldstr    aInstalledchann_0// "InstalledChannelUri"
0x1a8ed  ldsfld   class Microsoft.VisualStudio.Setup.UriStrictEqualityComparer Microsoft.VisualStudio.Setup.Cache.Instance::UriComparer
0x1a8f2  call     T0x2B0000CC
0x1a8f7  ret
```
