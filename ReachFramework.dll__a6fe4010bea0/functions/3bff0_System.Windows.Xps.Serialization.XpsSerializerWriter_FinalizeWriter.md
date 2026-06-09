# System.Windows.Xps.Serialization.XpsSerializerWriter::FinalizeWriter

- ea: `0x3bff0`
- end: `0x3c01c`
- name: `System.Windows.Xps.Serialization.XpsSerializerWriter::FinalizeWriter`
- size: `44`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x3b990`
- `0x3b9b0`
- `0x3ba50`
- `0x3ba70`
- `0x3bb10`
- `0x3bb30`
- `0x3bbd0`
- `0x3bbf0`
- `0x3bc90`
- `0x3bcb0`
- `0x3bf90`
- `0x3bfb0`

## callees

- `0x26040`

## pseudocode

```c

```

## disassembly

```asm
0x3bff0  ldarg.0
0x3bff1  ldfld    class System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.Serialization.XpsSerializerWriter::_xpsDocument
0x3bff6  callvirt instance void System.Windows.Xps.Packaging.XpsDocument::Close()
0x3bffb  ldarg.0
0x3bffc  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Serialization.XpsSerializerWriter::_package
0x3c001  callvirt instance void [WindowsBase]System.IO.Packaging.Package::Close()
0x3c006  ldarg.0
0x3c007  ldnull
0x3c008  stfld    class System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.Serialization.XpsSerializerWriter::_xpsDocument
0x3c00d  ldarg.0
0x3c00e  ldnull
0x3c00f  stfld    class [System.Printing]System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.Serialization.XpsSerializerWriter::_xpsDocumentWriter
0x3c014  ldarg.0
0x3c015  ldnull
0x3c016  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Serialization.XpsSerializerWriter::_package
0x3c01b  ret
```
