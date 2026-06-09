# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstalledChannelId

- ea: `0x1a810`
- end: `0x1a824`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstalledChannelId`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a818`: `InstalledChannelId`

## pseudocode

```c

```

## disassembly

```asm
0x1a810  ldarg.0
0x1a811  ldarg.0
0x1a812  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::installedChannelId
0x1a817  ldarg.1
0x1a818  ldstr    aInstalledchann// "InstalledChannelId"
0x1a81d  ldnull
0x1a81e  call     T0x2B0000C9
0x1a823  ret
```
