# System.Xml.Xsl.IlGen.OptimizerPatterns::Read

- ea: `0x409c0`
- end: `0x40a8d`
- name: `System.Xml.Xsl.IlGen.OptimizerPatterns::Read`
- size: `205`
- prototype: ``
- caller_count: `22`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xed0`
- `0x40af0`
- `0x42c40`
- `0x43650`
- `0x43860`
- `0x46190`
- `0x468e0`
- `0x471d0`
- `0x48eb0`
- `0x49160`
- `0x49a70`
- `0x49ad0`
- `0x4a190`
- `0x4a1a0`
- `0x4a1e0`
- `0x4bbe0`
- `0x4cc30`
- `0x4d200`
- `0x4d910`
- `0x4dc70`
- `0x4e510`
- `0x509c0`

## callees

- `0x2010`
- `0x23b0`
- `0x376c0`
- `0x37700`
- `0x409c0`
- `0x40c40`
- `0x40ce0`
- `0x41290`

## pseudocode

```c

```

## disassembly

```asm
0x409c0  ldarg.0
0x409c1  callvirt instance object System.Xml.Xsl.Qil.QilNode::get_Annotation()
0x409c6  isinst   System.Xml.Xsl.IlGen.XmlILAnnotation
0x409cb  stloc.0
0x409cc  ldloc.0
0x409cd  brtrue.s loc_409D2
0x409cf  ldnull
0x409d0  br.s     loc_409D8
0x409d2  ldloc.0
0x409d3  callvirt instance class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.XmlILAnnotation::get_Patterns()
0x409d8  stloc.1
0x409d9  ldloc.1
0x409da  brtrue   loc_40A8B
0x409df  ldarg.0
0x409e0  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x409e5  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_MaybeMany()
0x409ea  brtrue.s loc_40A25
0x409ec  volatile.
0x409ee  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::ZeroOrOneDefault
0x409f3  brtrue.s loc_40A1B
0x409f5  newobj   instance void System.Xml.Xsl.IlGen.OptimizerPatterns::.ctor()
0x409fa  stloc.1
0x409fb  ldloc.1
0x409fc  ldc.i4.6
0x409fd  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40a02  ldloc.1
0x40a03  ldc.i4.s 0xA
0x40a05  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40a0a  ldloc.1
0x40a0b  ldc.i4.1
0x40a0c  stfld    bool System.Xml.Xsl.IlGen.OptimizerPatterns::isReadOnly
0x40a11  ldloc.1
0x40a12  volatile.
0x40a14  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::ZeroOrOneDefault
0x40a19  br.s     loc_40A8B
0x40a1b  volatile.
0x40a1d  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::ZeroOrOneDefault
0x40a22  stloc.1
0x40a23  br.s     loc_40A8B
0x40a25  ldarg.0
0x40a26  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x40a2b  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsDod()
0x40a30  brfalse.s loc_40A63
0x40a32  volatile.
0x40a34  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::DodDefault
0x40a39  brtrue.s loc_40A59
0x40a3b  newobj   instance void System.Xml.Xsl.IlGen.OptimizerPatterns::.ctor()
0x40a40  stloc.1
0x40a41  ldloc.1
0x40a42  ldc.i4.6
0x40a43  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x40a48  ldloc.1
0x40a49  ldc.i4.1
0x40a4a  stfld    bool System.Xml.Xsl.IlGen.OptimizerPatterns::isReadOnly
0x40a4f  ldloc.1
0x40a50  volatile.
0x40a52  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::DodDefault
0x40a57  br.s     loc_40A8B
0x40a59  volatile.
0x40a5b  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::DodDefault
0x40a60  stloc.1
0x40a61  br.s     loc_40A8B
0x40a63  volatile.
0x40a65  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::MaybeManyDefault
0x40a6a  brtrue.s loc_40A83
0x40a6c  newobj   instance void System.Xml.Xsl.IlGen.OptimizerPatterns::.ctor()
0x40a71  stloc.1
0x40a72  ldloc.1
0x40a73  ldc.i4.1
0x40a74  stfld    bool System.Xml.Xsl.IlGen.OptimizerPatterns::isReadOnly
0x40a79  ldloc.1
0x40a7a  volatile.
0x40a7c  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::MaybeManyDefault
0x40a81  br.s     loc_40A8B
0x40a83  volatile.
0x40a85  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::MaybeManyDefault
0x40a8a  stloc.1
0x40a8b  ldloc.1
0x40a8c  ret
```
