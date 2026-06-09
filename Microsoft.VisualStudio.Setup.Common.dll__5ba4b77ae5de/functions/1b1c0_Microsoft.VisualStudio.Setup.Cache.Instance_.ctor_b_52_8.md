# Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_8

- ea: `0x1b1c0`
- end: `0x1b1cc`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::<.ctor>b__52_8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1aff0`

## string_xrefs

- `0x1b1c1`: `PreviousLayoutPaths`

## pseudocode

```c

```

## disassembly

```asm
0x1b1c0  ldarg.0
0x1b1c1  ldstr    aPreviouslayout// "PreviousLayoutPaths"
0x1b1c6  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged([opt] string propertyName)
0x1b1cb  ret
```
