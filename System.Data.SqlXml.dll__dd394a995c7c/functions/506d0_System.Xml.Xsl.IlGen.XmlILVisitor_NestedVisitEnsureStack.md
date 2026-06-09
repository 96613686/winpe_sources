# System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack

- ea: `0x506d0`
- end: `0x506e3`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack`
- size: `19`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x4b0e0`
- `0x4b1b0`
- `0x4b230`
- `0x4bbe0`
- `0x4bdc0`
- `0x4c490`
- `0x4c570`
- `0x4c5b0`
- `0x4c800`
- `0x4cc30`
- `0x4d740`
- `0x4e130`
- `0x4e330`
- `0x4e3a0`
- `0x4e4a0`
- `0x4e510`
- `0x4e600`
- `0x4e7a0`
- `0x4e900`
- `0x4eb20`
- `0x4f530`
- `0x4f5d0`
- `0x4f610`
- `0x4f8b0`
- `0x4f8f0`
- `0x4f940`
- `0x4fc30`
- `0x4fd90`
- `0x4fe10`
- `0x506f0`

## callees

- `0x40670`
- `0x50650`

## pseudocode

```c

```

## disassembly

```asm
0x506d0  ldarg.0
0x506d1  ldarg.1
0x506d2  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd)
0x506d7  ldarg.0
0x506d8  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x506dd  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStack()
0x506e2  ret
```
