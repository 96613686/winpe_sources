# Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_9

- ea: `0x1b1d0`
- end: `0x1b1e2`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_9`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1b000`

## string_xrefs

- `0x1b1d7`: `GroupConfigFiles`

## pseudocode

```c

```

## disassembly

```asm
0x1b1d0  ldarg.0
0x1b1d1  ldarg.0
0x1b1d2  ldflda   bool Microsoft.VisualStudio.Setup.Cache.Instance::groupConfigsChanged
0x1b1d7  ldstr    aGroupconfigfil// "GroupConfigFiles"
0x1b1dc  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged(bool& field, [opt] string propertyName)
0x1b1e1  ret
```
