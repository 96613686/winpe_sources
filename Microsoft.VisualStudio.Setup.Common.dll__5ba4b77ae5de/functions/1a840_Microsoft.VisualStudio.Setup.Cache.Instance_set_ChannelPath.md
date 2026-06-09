# Microsoft.VisualStudio.Setup.Cache.Instance::set_ChannelPath

- ea: `0x1a840`
- end: `0x1a854`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_ChannelPath`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a848`: `ChannelPath`

## pseudocode

```c

```

## disassembly

```asm
0x1a840  ldarg.0
0x1a841  ldarg.0
0x1a842  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::channelPath
0x1a847  ldarg.1
0x1a848  ldstr    aChannelpath// "ChannelPath"
0x1a84d  ldnull
0x1a84e  call     T0x2B0000C9
0x1a853  ret
```
