# Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_11

- ea: `0x1b210`
- end: `0x1b222`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_11`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1b000`

## string_xrefs

- `0x1b217`: `PendingGroupFileRenames`

## pseudocode

```c

```

## disassembly

```asm
0x1b210  ldarg.0
0x1b211  ldarg.0
0x1b212  ldflda   bool Microsoft.VisualStudio.Setup.Cache.Instance::groupConfigsChanged
0x1b217  ldstr    aPendinggroupfi// "PendingGroupFileRenames"
0x1b21c  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged(bool& field, [opt] string propertyName)
0x1b221  ret
```
