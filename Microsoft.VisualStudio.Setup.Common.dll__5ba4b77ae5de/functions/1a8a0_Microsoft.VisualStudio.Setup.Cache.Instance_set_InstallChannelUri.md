# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallChannelUri

- ea: `0x1a8a0`
- end: `0x1a8b8`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallChannelUri`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a8a8`: `InstallChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x1a8a0  ldarg.0
0x1a8a1  ldarg.0
0x1a8a2  ldflda   class [System]System.Uri Microsoft.VisualStudio.Setup.Cache.Instance::installChannelUri
0x1a8a7  ldarg.1
0x1a8a8  ldstr    aInstallchannel// "InstallChannelUri"
0x1a8ad  ldsfld   class Microsoft.VisualStudio.Setup.UriStrictEqualityComparer Microsoft.VisualStudio.Setup.Cache.Instance::UriComparer
0x1a8b2  call     T0x2B0000CC
0x1a8b7  ret
```
