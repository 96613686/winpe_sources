# System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType

- ea: `0x50a90`
- end: `0x50aa1`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType`
- size: `17`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x4a9f0`
- `0x4aa60`
- `0x4ad40`
- `0x4b810`
- `0x4bdc0`
- `0x4c290`
- `0x4c2c0`
- `0x4c2f0`
- `0x4c320`
- `0x4c350`
- `0x4c490`
- `0x4c520`
- `0x4d420`
- `0x4d520`
- `0x4d740`
- `0x4dc70`
- `0x4e720`
- `0x4f110`
- `0x50650`
- `0x50670`
- `0x50780`
- `0x509c0`

## callees

- `0x1ff0`
- `0x376c0`
- `0x4a2a0`

## pseudocode

```c

```

## disassembly

```asm
0x50a90  ldarg.1
0x50a91  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x50a96  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryType::get_Prime()
0x50a9b  call     class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILTypeHelper::GetStorageType(class System.Xml.Xsl.XmlQueryType qyTyp)
0x50aa0  ret
```
