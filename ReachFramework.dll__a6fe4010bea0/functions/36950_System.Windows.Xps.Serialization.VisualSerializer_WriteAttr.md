# System.Windows.Xps.Serialization.VisualSerializer::WriteAttr

- ea: `0x36950`
- end: `0x36964`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WriteAttr`
- size: `20`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x36a20`
- `0x36b30`
- `0x36b80`
- `0x36fb0`
- `0x37110`
- `0x37580`
- `0x37870`
- `0x384e0`
- `0x38840`
- `0x38ca0`
- `0x38ea0`

## callees

- `0x366d0`

## pseudocode

```c

```

## disassembly

```asm
0x36950  ldarg.0
0x36951  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.VisualSerializer::_writer
0x36956  ldarg.1
0x36957  ldarg.0
0x36958  ldarg.2
0x36959  call     instance string System.Windows.Xps.Serialization.VisualSerializer::GetString(object obj)
0x3695e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x36963  ret
```
