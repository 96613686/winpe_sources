# System.Xml.Xsl.IlGen.OptimizerPatterns::Write

- ea: `0x40a90`
- end: `0x40aea`
- name: `System.Xml.Xsl.IlGen.OptimizerPatterns::Write`
- size: `90`
- prototype: ``
- caller_count: `35`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x40af0`
- `0x410a0`
- `0x42b90`
- `0x42c40`
- `0x43020`
- `0x43860`
- `0x43b00`
- `0x43cf0`
- `0x44b30`
- `0x44e60`
- `0x455f0`
- `0x45890`
- `0x45ac0`
- `0x45cf0`
- `0x46190`
- `0x468e0`
- `0x471d0`
- `0x479d0`
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
- `0x48440`
- `0x48ad0`
- `0x492f0`
- `0x49380`
- `0x49400`
- `0x4a170`

## callees

- `0x2010`
- `0x23b0`
- `0x376c0`
- `0x40a90`
- `0x40c40`
- `0x40ce0`
- `0x411d0`
- `0x41290`
- `0x412a0`

## pseudocode

```c

```

## disassembly

```asm
0x40a90  ldarg.0
0x40a91  call     class System.Xml.Xsl.IlGen.XmlILAnnotation System.Xml.Xsl.IlGen.XmlILAnnotation::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x40a96  stloc.0
0x40a97  ldloc.0
0x40a98  callvirt instance class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.XmlILAnnotation::get_Patterns()
0x40a9d  stloc.1
0x40a9e  ldloc.1
0x40a9f  brfalse.s loc_40AA9
0x40aa1  ldloc.1
0x40aa2  ldfld    bool System.Xml.Xsl.IlGen.OptimizerPatterns::isReadOnly
0x40aa7  brfalse.s loc_40AE8
0x40aa9  newobj   instance void System.Xml.Xsl.IlGen.OptimizerPatterns::.ctor()
0x40aae  stloc.1
0x40aaf  ldloc.0
0x40ab0  ldloc.1
0x40ab1  callvirt instance void System.Xml.Xsl.IlGen.XmlILAnnotation::set_Patterns(class System.Xml.Xsl.IlGen.OptimizerPatterns value)
0x40ab6  ldarg.0
0x40ab7  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x40abc  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_MaybeMany()
0x40ac1  brtrue.s loc_40AD4
0x40ac3  ldloc.1
0x40ac4  ldc.i4.6
0x40ac5  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40aca  ldloc.1
0x40acb  ldc.i4.s 0xA
0x40acd  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40ad2  br.s     loc_40AE8
0x40ad4  ldarg.0
0x40ad5  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x40ada  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsDod()
0x40adf  brfalse.s loc_40AE8
0x40ae1  ldloc.1
0x40ae2  ldc.i4.6
0x40ae3  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40ae8  ldloc.1
0x40ae9  ret
```
