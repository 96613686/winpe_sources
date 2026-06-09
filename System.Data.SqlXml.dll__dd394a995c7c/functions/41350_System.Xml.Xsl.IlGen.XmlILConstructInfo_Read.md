# System.Xml.Xsl.IlGen.XmlILConstructInfo::Read

- ea: `0x41350`
- end: `0x41398`
- name: `System.Xml.Xsl.IlGen.XmlILConstructInfo::Read`
- size: `72`
- prototype: ``
- caller_count: `22`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xb90`
- `0x41050`
- `0x410a0`
- `0x42b20`
- `0x489d0`
- `0x4a1e0`
- `0x4ad40`
- `0x4af60`
- `0x4b1b0`
- `0x4b230`
- `0x4b810`
- `0x4bd10`
- `0x4dc70`
- `0x4e1a0`
- `0x4e270`
- `0x4e3a0`
- `0x4e4a0`
- `0x50210`
- `0x50270`
- `0x502f0`
- `0x50340`
- `0x505b0`

## callees

- `0x37700`
- `0x41270`
- `0x41350`
- `0x413d0`

## pseudocode

```c

```

## disassembly

```asm
0x41350  ldarg.0
0x41351  callvirt instance object System.Xml.Xsl.Qil.QilNode::get_Annotation()
0x41356  isinst   System.Xml.Xsl.IlGen.XmlILAnnotation
0x4135b  stloc.0
0x4135c  ldloc.0
0x4135d  brtrue.s loc_41362
0x4135f  ldnull
0x41360  br.s     loc_41368
0x41362  ldloc.0
0x41363  callvirt instance class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILAnnotation::get_ConstructInfo()
0x41368  stloc.1
0x41369  ldloc.1
0x4136a  brtrue.s loc_41396
0x4136c  volatile.
0x4136e  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Default
0x41373  brtrue.s loc_4138E
0x41375  ldc.i4.s 9
0x41377  newobj   instance void System.Xml.Xsl.IlGen.XmlILConstructInfo::.ctor(valuetype System.Xml.Xsl.Qil.QilNodeType nodeType)
0x4137c  stloc.1
0x4137d  ldloc.1
0x4137e  ldc.i4.1
0x4137f  stfld    bool System.Xml.Xsl.IlGen.XmlILConstructInfo::isReadOnly
0x41384  ldloc.1
0x41385  volatile.
0x41387  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Default
0x4138c  br.s     loc_41396
0x4138e  volatile.
0x41390  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Default
0x41395  stloc.1
0x41396  ldloc.1
0x41397  ret
```
