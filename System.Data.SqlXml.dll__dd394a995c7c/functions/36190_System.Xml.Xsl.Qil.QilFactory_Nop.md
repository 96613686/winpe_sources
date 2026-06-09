# System.Xml.Xsl.Qil.QilFactory::Nop

- ea: `0x36190`
- end: `0x361ad`
- name: `System.Xml.Xsl.Qil.QilFactory::Nop`
- size: `29`
- prototype: ``
- caller_count: `76`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x37c10`
- `0x419a0`
- `0x42e30`
- `0x42f00`
- `0x42f50`
- `0x430e0`
- `0x43220`
- `0x43360`
- `0x43430`
- `0x43650`
- `0x43860`
- `0x43b00`
- `0x43cf0`
- `0x43f00`
- `0x43fa0`
- `0x44040`
- `0x440e0`
- `0x44180`
- `0x44310`
- `0x44450`
- `0x44540`
- `0x44680`
- `0x44770`
- `0x44860`
- `0x44900`
- `0x44a90`
- `0x44b30`
- `0x44e60`
- `0x455f0`
- `0x45890`
- `0x45ac0`
- `0x45cf0`
- `0x45f20`
- `0x45ff0`
- `0x460c0`
- `0x46190`
- `0x468e0`
- `0x47070`
- `0x471d0`
- `0x47db0`
- `0x47e50`
- `0x47f30`
- `0x47fd0`
- `0x48070`
- `0x48100`
- `0x48190`
- `0x48210`
- `0x48290`
- `0x48310`
- `0x483b0`

## callees

- `0x376d0`
- `0x39b40`
- `0x3a4e0`

## pseudocode

```c

```

## disassembly

```asm
0x36190  ldc.i4.s 0xB
0x36192  ldarg.1
0x36193  newobj   instance void System.Xml.Xsl.Qil.QilUnary::.ctor(valuetype System.Xml.Xsl.Qil.QilNodeType nodeType, class System.Xml.Xsl.Qil.QilNode child)
0x36198  stloc.0
0x36199  ldloc.0
0x3619a  ldarg.0
0x3619b  ldfld    class System.Xml.Xsl.Qil.QilTypeChecker System.Xml.Xsl.Qil.QilFactory::typeCheck
0x361a0  ldloc.0
0x361a1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilTypeChecker::CheckNop(class System.Xml.Xsl.Qil.QilUnary node)
0x361a6  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_XmlType(class System.Xml.Xsl.XmlQueryType value)
0x361ab  ldloc.0
0x361ac  ret
```
