# System.Windows.Documents.TextRangeSerialization::WriteRootFlowDocument

- ea: `0x11d680`
- end: `0x11d79b`
- name: `System.Windows.Documents.TextRangeSerialization::WriteRootFlowDocument`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11ce50`

## callees

- `0xe43d0`
- `0x111f80`
- `0x11d680`
- `0x11d7a0`
- `0x11d850`
- `0x11d900`
- `0x11dbd0`

## string_xrefs

- `0x11d6f6`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`
- `0x11d706`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`
- `0x11d701`: `xmlns`
- `0x11d711`: `xml:space`

## pseudocode

```c

```

## disassembly

```asm
0x11d680  ldarg.s  5
0x11d682  brfalse.s loc_11D691
0x11d684  ldtoken  System.Windows.Documents.FlowDocument
0x11d689  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d68e  stloc.0
0x11d68f  br.s     loc_11D6EF
0x11d691  ldarg.1
0x11d692  callvirt instance class [mscorlib]System.Type System.Windows.Documents.ITextPointer::get_ParentType()
0x11d697  stloc.2
0x11d698  ldloc.2
0x11d699  ldnull
0x11d69a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11d69f  brtrue.s loc_11D6D7
0x11d6a1  ldtoken  System.Windows.Documents.Paragraph
0x11d6a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d6ab  ldloc.2
0x11d6ac  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x11d6b1  brtrue.s loc_11D6D7
0x11d6b3  ldtoken  System.Windows.Documents.Inline
0x11d6b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d6bd  ldloc.2
0x11d6be  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x11d6c3  brfalse.s loc_11D6E4
0x11d6c5  ldtoken  System.Windows.Documents.AnchoredBlock
0x11d6ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d6cf  ldloc.2
0x11d6d0  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x11d6d5  brtrue.s loc_11D6E4
0x11d6d7  ldtoken  System.Windows.Documents.Span
0x11d6dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d6e1  stloc.0
0x11d6e2  br.s     loc_11D6EF
0x11d6e4  ldtoken  System.Windows.Documents.Section
0x11d6e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d6ee  stloc.0
0x11d6ef  ldarg.2
0x11d6f0  ldloc.0
0x11d6f1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x11d6f6  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0x11d6fb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x11d700  ldarg.2
0x11d701  ldstr    aXmlns// "xmlns"
0x11d706  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0x11d70b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x11d710  ldarg.2
0x11d711  ldstr    aXmlSpace// "xml:space"
0x11d716  ldstr    aPreserve// "preserve"
0x11d71b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x11d720  newobj   instance void [WindowsBase]System.Windows.DependencyObject::.ctor()
0x11d725  stloc.1
0x11d726  ldarg.s  5
0x11d728  brfalse.s loc_11D73E
0x11d72a  ldarg.1
0x11d72b  castclass System.Windows.Documents.TextPointer
0x11d730  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x11d735  ldarg.2
0x11d736  ldloc.1
0x11d737  call     void System.Windows.Documents.TextRangeSerialization::WriteInheritablePropertiesForFlowDocument(class [WindowsBase]System.Windows.DependencyObject context, class [System.Xml]System.Xml.XmlWriter xmlWriter, class [WindowsBase]System.Windows.DependencyObject complexProperties)
0x11d73c  br.s     loc_11D748
0x11d73e  ldloc.0
0x11d73f  ldarg.1
0x11d740  ldarg.2
0x11d741  ldc.i4.0
0x11d742  ldloc.1
0x11d743  call     void System.Windows.Documents.TextRangeSerialization::WriteInheritableProperties(class [mscorlib]System.Type elementTypeStandardized, class System.Windows.Documents.ITextPointer context, class [System.Xml]System.Xml.XmlWriter xmlWriter, bool onlyAffected, class [WindowsBase]System.Windows.DependencyObject complexProperties)
0x11d748  ldloc.0
0x11d749  ldtoken  System.Windows.Documents.Span
0x11d74e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d753  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11d758  brfalse.s loc_11D76D
0x11d75a  ldtoken  System.Windows.Documents.Span
0x11d75f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d764  ldarg.1
0x11d765  ldarg.2
0x11d766  ldc.i4.0
0x11d767  ldloc.1
0x11d768  call     void System.Windows.Documents.TextRangeSerialization::WriteNoninheritableProperties(class [mscorlib]System.Type elementTypeStandardized, class System.Windows.Documents.ITextPointer context, class [System.Xml]System.Xml.XmlWriter xmlWriter, bool onlyAffected, class [WindowsBase]System.Windows.DependencyObject complexProperties)
0x11d76d  ldloc.0
0x11d76e  ldtoken  System.Windows.Documents.Section
0x11d773  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11d778  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11d77d  ldarg.s  4
0x11d77f  and
0x11d780  brfalse.s loc_11D792
0x11d782  ldarg.2
0x11d783  ldstr    aHastrailingpar// "HasTrailingParagraphBreakOnPaste"
0x11d788  ldstr    aFalse// "False"
0x11d78d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x11d792  ldarg.2
0x11d793  ldloc.1
0x11d794  ldloc.0
0x11d795  call     void System.Windows.Documents.TextRangeSerialization::WriteComplexProperties(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [WindowsBase]System.Windows.DependencyObject complexProperties, class [mscorlib]System.Type elementType)
0x11d79a  ret
```
