# System.Xml.Xsl.Qil.QilVisitor::VisitChildren

- ea: `0x3a600`
- end: `0x3a63b`
- name: `System.Xml.Xsl.Qil.QilVisitor::VisitChildren`
- size: `59`
- prototype: ``
- caller_count: `113`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x385a0`
- `0x3ae40`
- `0x3ae50`
- `0x3ae60`
- `0x3ae70`
- `0x3ae80`
- `0x3ae90`
- `0x3aea0`
- `0x3aeb0`
- `0x3aec0`
- `0x3aed0`
- `0x3aee0`
- `0x3aef0`
- `0x3af00`
- `0x3af10`
- `0x3af20`
- `0x3af40`
- `0x3af60`
- `0x3af80`
- `0x3af90`
- `0x3afa0`
- `0x3afb0`
- `0x3afc0`
- `0x3afd0`
- `0x3afe0`
- `0x3aff0`
- `0x3b000`
- `0x3b010`
- `0x3b020`
- `0x3b030`
- `0x3b040`
- `0x3b050`
- `0x3b060`
- `0x3b070`
- `0x3b080`
- `0x3b090`
- `0x3b0a0`
- `0x3b0b0`
- `0x3b0c0`
- `0x3b0d0`
- `0x3b0e0`
- `0x3b0f0`
- `0x3b100`
- `0x3b110`
- `0x3b120`
- `0x3b130`
- `0x3b140`
- `0x3b150`
- `0x3b160`
- `0x3b170`

## callees

- `0x37740`
- `0x37750`
- `0x3a600`
- `0x3a640`
- `0x3a690`
- `0x3adc0`

## pseudocode

```c

```

## disassembly

```asm
0x3a600  ldc.i4.0
0x3a601  stloc.0
0x3a602  br.s     loc_3A630
0x3a604  ldarg.0
0x3a605  ldarg.1
0x3a606  ldloc.0
0x3a607  callvirt instance bool System.Xml.Xsl.Qil.QilVisitor::IsReference(class System.Xml.Xsl.Qil.QilNode parent, int32 childNum)
0x3a60c  brfalse.s loc_3A61E
0x3a60e  ldarg.0
0x3a60f  ldarg.1
0x3a610  ldloc.0
0x3a611  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3a616  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitReference(class System.Xml.Xsl.Qil.QilNode n)
0x3a61b  pop
0x3a61c  br.s     loc_3A62C
0x3a61e  ldarg.0
0x3a61f  ldarg.1
0x3a620  ldloc.0
0x3a621  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3a626  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x3a62b  pop
0x3a62c  ldloc.0
0x3a62d  ldc.i4.1
0x3a62e  add
0x3a62f  stloc.0
0x3a630  ldloc.0
0x3a631  ldarg.1
0x3a632  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x3a637  blt.s    loc_3A604
0x3a639  ldarg.1
0x3a63a  ret
```
