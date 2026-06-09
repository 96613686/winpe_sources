# System.Xml.Xsl.IlGen.XmlILVisitor::CopySequence

- ea: `0x4b030`
- end: `0x4b0dd`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::CopySequence`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x4af60`

## callees

- `0x2370`
- `0x376c0`
- `0x3a690`
- `0x3f1d0`
- `0x3f3e0`
- `0x407e0`
- `0x407f0`
- `0x40820`
- `0x4b030`
- `0x50210`
- `0x50270`

## string_xrefs

- `0x4b0a3`: `$$$copyTemp`

## pseudocode

```c

```

## disassembly

```asm
0x4b030  ldarg.1
0x4b031  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4b036  stloc.0
0x4b037  ldarg.0
0x4b038  ldarg.1
0x4b039  ldloca.s 1
0x4b03b  ldloca.s 2
0x4b03d  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartWriterLoop(class System.Xml.Xsl.Qil.QilNode nd, [out] bool& hasOnEnd, [out] valuetype [mscorlib]System.Reflection.Emit.Label& lblOnEnd)
0x4b042  ldloc.0
0x4b043  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4b048  brfalse.s loc_4B07A
0x4b04a  ldarg.0
0x4b04b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b050  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryOutput()
0x4b055  ldarg.0
0x4b056  ldarg.1
0x4b057  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4b05c  pop
0x4b05d  ldarg.0
0x4b05e  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4b063  ldarg.1
0x4b064  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4b069  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4b06e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b073  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4b078  br.s     loc_4B0B8
0x4b07a  ldarg.0
0x4b07b  ldarg.1
0x4b07c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4b081  pop
0x4b082  ldarg.0
0x4b083  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4b088  ldarg.1
0x4b089  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4b08e  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4b093  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b098  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4b09d  ldarg.0
0x4b09e  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4b0a3  ldstr    aCopytemp// "$$$copyTemp"
0x4b0a8  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoStackNoCache(string locName)
0x4b0ad  ldarg.0
0x4b0ae  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b0b3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryOutput()
0x4b0b8  ldarg.0
0x4b0b9  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4b0be  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x4b0c3  ldarg.0
0x4b0c4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b0c9  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::WriteItem
0x4b0ce  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4b0d3  ldarg.0
0x4b0d4  ldarg.1
0x4b0d5  ldloc.1
0x4b0d6  ldloc.2
0x4b0d7  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndWriterLoop(class System.Xml.Xsl.Qil.QilNode nd, bool hasOnEnd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4b0dc  ret
```
