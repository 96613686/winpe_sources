# System.Xml.Xsl.IlGen.XmlILVisitor::StartLetBinding

- ea: `0x4d420`
- end: `0x4d4b0`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::StartLetBinding`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x4d200`

## callees

- `0x2370`
- `0x35d30`
- `0x37100`
- `0x376c0`
- `0x38cd0`
- `0x3fe00`
- `0x40260`
- `0x405a0`
- `0x406e0`
- `0x40700`
- `0x4d420`
- `0x50490`
- `0x504f0`
- `0x505b0`
- `0x50a90`

## string_xrefs

- `0x4d46e`: `$$$cache`
- `0x4d49e`: `$$$cache`

## pseudocode

```c

```

## disassembly

```asm
0x4d420  ldarg.0
0x4d421  ldarg.1
0x4d422  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d427  ldarg.0
0x4d428  ldarg.1
0x4d429  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4d42e  ldarg.0
0x4d42f  ldarg.1
0x4d430  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4d435  ldarg.1
0x4d436  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d43b  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4d440  ldc.i4.0
0x4d441  ceq
0x4d443  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4d448  ldarg.0
0x4d449  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.IlGen.XmlILVisitor::qil
0x4d44e  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x4d453  brfalse.s loc_4D498
0x4d455  ldarg.1
0x4d456  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x4d45b  brfalse.s loc_4D498
0x4d45d  ldarg.0
0x4d45e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d463  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::DebugStartScope()
0x4d468  ldarg.0
0x4d469  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d46e  ldstr    aCache// "$$$cache"
0x4d473  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureLocal(string locName)
0x4d478  ldarg.0
0x4d479  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d47e  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x4d483  stloc.0
0x4d484  ldloca.s 0
0x4d486  call     instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.StorageDescriptor::get_LocalLocation()
0x4d48b  ldarg.1
0x4d48c  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x4d491  callvirt instance void [mscorlib]System.Reflection.Emit.LocalBuilder::SetLocalSymInfo(string)
0x4d496  br.s     loc_4D4A8
0x4d498  ldarg.0
0x4d499  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d49e  ldstr    aCache// "$$$cache"
0x4d4a3  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoStack(string locName)
0x4d4a8  ldarg.0
0x4d4a9  ldarg.1
0x4d4aa  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d4af  ret
```
