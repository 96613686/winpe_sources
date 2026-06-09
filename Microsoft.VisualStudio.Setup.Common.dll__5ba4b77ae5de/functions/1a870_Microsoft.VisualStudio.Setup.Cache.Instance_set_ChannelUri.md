# Microsoft.VisualStudio.Setup.Cache.Instance::set_ChannelUri

- ea: `0x1a870`
- end: `0x1a888`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_ChannelUri`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a878`: `ChannelUri`

## pseudocode

```c

```

## disassembly

```asm
0x1a870  ldarg.0
0x1a871  ldarg.0
0x1a872  ldflda   class [System]System.Uri Microsoft.VisualStudio.Setup.Cache.Instance::channelUri
0x1a877  ldarg.1
0x1a878  ldstr    aChanneluri// "ChannelUri"
0x1a87d  ldsfld   class Microsoft.VisualStudio.Setup.UriStrictEqualityComparer Microsoft.VisualStudio.Setup.Cache.Instance::UriComparer
0x1a882  call     T0x2B0000CC
0x1a887  ret
```
