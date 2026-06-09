# Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged

- ea: `0x1aff0`
- end: `0x1affe`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged`
- size: `14`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b020`
- `0x1b130`
- `0x1b140`
- `0x1b170`
- `0x1b180`
- `0x1b190`
- `0x1b1a0`
- `0x1b1b0`
- `0x1b1c0`
- `0x1db20`

## callees

- `0x1b000`

## pseudocode

```c

```

## disassembly

```asm
0x1aff0  ldarg.0
0x1aff1  ldarg.0
0x1aff2  ldflda   bool Microsoft.VisualStudio.Setup.Cache.Instance::baseChanged
0x1aff7  ldarg.1
0x1aff8  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged(bool& field, [opt] string propertyName)
0x1affd  ret
```
