# Microsoft.VisualStudio.Setup.Cache.Instance::set_EnginePath

- ea: `0x1a5c0`
- end: `0x1a5d4`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_EnginePath`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a5c8`: `EnginePath`

## pseudocode

```c

```

## disassembly

```asm
0x1a5c0  ldarg.0
0x1a5c1  ldarg.0
0x1a5c2  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::enginePath
0x1a5c7  ldarg.1
0x1a5c8  ldstr    aEnginepath// "EnginePath"
0x1a5cd  ldnull
0x1a5ce  call     T0x2B0000C9
0x1a5d3  ret
```
