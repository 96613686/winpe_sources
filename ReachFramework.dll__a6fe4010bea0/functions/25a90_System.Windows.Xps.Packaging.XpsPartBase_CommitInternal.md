# System.Windows.Xps.Packaging.XpsPartBase::CommitInternal

- ea: `0x25a90`
- end: `0x25aa0`
- name: `System.Windows.Xps.Packaging.XpsPartBase::CommitInternal`
- size: `16`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x20c20`
- `0x20f80`
- `0x20fa0`
- `0x21550`
- `0x21560`
- `0x21c90`
- `0x21cb0`
- `0x22750`
- `0x23220`
- `0x23240`
- `0x26020`
- `0x26050`
- `0x26490`
- `0x264f0`

## callees

- `0x25a90`

## pseudocode

```c

```

## disassembly

```asm
0x25a90  ldarg.0
0x25a91  ldfld    class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::_xpsManager
0x25a96  brfalse.s loc_25A9F
0x25a98  ldarg.0
0x25a99  ldnull
0x25a9a  stfld    class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::_xpsManager
0x25a9f  ret
```
