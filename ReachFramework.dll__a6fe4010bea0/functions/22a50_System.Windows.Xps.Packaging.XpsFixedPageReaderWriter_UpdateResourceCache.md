# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::UpdateResourceCache

- ea: `0x22a50`
- end: `0x22a66`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::UpdateResourceCache`
- size: `22`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x220f0`
- `0x22110`
- `0x22130`
- `0x22150`
- `0x22180`
- `0x223c0`
- `0x225b0`
- `0x225e0`
- `0x22610`
- `0x22720`
- `0x22800`
- `0x22870`

## callees

- `0x22a50`
- `0x22a70`

## pseudocode

```c

```

## disassembly

```asm
0x22a50  ldarg.0
0x22a51  ldfld    bool System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_hasParsedResources
0x22a56  brtrue.s loc_22A65
0x22a58  ldarg.0
0x22a59  call     instance void System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::ParseResources()
0x22a5e  ldarg.0
0x22a5f  ldc.i4.1
0x22a60  stfld    bool System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_hasParsedResources
0x22a65  ret
```
