# Microsoft.VisualStudio.Setup.Cache.Instance::set_LayoutPath

- ea: `0x1a700`
- end: `0x1a714`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_LayoutPath`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a708`: `LayoutPath`

## pseudocode

```c

```

## disassembly

```asm
0x1a700  ldarg.0
0x1a701  ldarg.0
0x1a702  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::layoutPath
0x1a707  ldarg.1
0x1a708  ldstr    aLayoutpath// "LayoutPath"
0x1a70d  ldnull
0x1a70e  call     T0x2B0000C9
0x1a713  ret
```
