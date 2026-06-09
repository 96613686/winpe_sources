# System.Windows.Annotations.ContentLocator::ReadXml

- ea: `0x1d3fe0`
- end: `0x1d4258`
- name: `System.Windows.Annotations.ContentLocator::ReadXml`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38c70`
- `0x1cf680`
- `0x1cf6e0`
- `0x1d3870`
- `0x1d3a00`
- `0x1d3a10`
- `0x1d3fe0`

## string_xrefs

- `0x1d3fe3`: `reader`
- `0x1d4091`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d4019`: `InvalidXmlContent`
- `0x1d41a8`: `InvalidXmlContent`
- `0x1d41cf`: `InvalidXmlContent`

## pseudocode

```c

```

## disassembly

```asm
0x1d3fe0  ldarg.1
0x1d3fe1  brtrue.s loc_1D3FEE
0x1d3fe3  ldstr    aReader// "reader"
0x1d3fe8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d3fed  throw
0x1d3fee  ldarg.1
0x1d3fef  ldstr    aContentlocator_0// "ContentLocator"
0x1d3ff4  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1d3ff9  ldarg.1
0x1d3ffa  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1d3fff  brtrue   loc_1D4250
0x1d4004  ldarg.1
0x1d4005  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d400a  pop
0x1d400b  br       loc_1D422E
0x1d4010  ldc.i4.1
0x1d4011  ldarg.1
0x1d4012  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d4017  beq.s    loc_1D4037
0x1d4019  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1d401e  ldc.i4.1
0x1d401f  newarr   [mscorlib]System.Object
0x1d4024  dup
0x1d4025  ldc.i4.0
0x1d4026  ldstr    aContentlocator_0// "ContentLocator"
0x1d402b  stelem.ref
0x1d402c  call     string System.Windows.SR::Get(string id, object[] args)
0x1d4031  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d4036  throw
0x1d4037  ldarg.1
0x1d4038  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d403d  ldarg.1
0x1d403e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1d4043  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x1d4048  newobj   instance void System.Windows.Annotations.ContentLocatorPart::.ctor(class [System.Xml]System.Xml.XmlQualifiedName partType)
0x1d404d  stloc.0
0x1d404e  ldarg.1
0x1d404f  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1d4054  brtrue   loc_1D421B
0x1d4059  ldarg.1
0x1d405a  ldloc.0
0x1d405b  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d4060  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1d4065  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1d406a  ldarg.1
0x1d406b  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d4070  pop
0x1d4071  br       loc_1D41F3
0x1d4076  ldstr    aItem_1// "Item"
0x1d407b  ldarg.1
0x1d407c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d4081  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d4086  brfalse  loc_1D41CF
0x1d408b  ldarg.1
0x1d408c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1d4091  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d4096  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d409b  brfalse  loc_1D41CF
0x1d40a0  ldnull
0x1d40a1  stloc.1
0x1d40a2  ldnull
0x1d40a3  stloc.2
0x1d40a4  br.s     loc_1D410D
0x1d40a6  ldarg.1
0x1d40a7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d40ac  stloc.s  4
0x1d40ae  ldloc.s  4
0x1d40b0  ldstr    aName// "Name"
0x1d40b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d40ba  brtrue.s loc_1D40CC
0x1d40bc  ldloc.s  4
0x1d40be  ldstr    aValue_0// "Value"
0x1d40c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d40c8  brtrue.s loc_1D40D5
0x1d40ca  br.s     loc_1D40DE
0x1d40cc  ldarg.1
0x1d40cd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x1d40d2  stloc.1
0x1d40d3  br.s     loc_1D410D
0x1d40d5  ldarg.1
0x1d40d6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x1d40db  stloc.2
0x1d40dc  br.s     loc_1D410D
0x1d40de  ldarg.1
0x1d40df  call     bool System.Windows.Annotations.Annotation::IsNamespaceDeclaration(class [System.Xml]System.Xml.XmlReader reader)
0x1d40e4  brtrue.s loc_1D410D
0x1d40e6  ldstr    aUnexpectedattr// "UnexpectedAttribute"
0x1d40eb  ldc.i4.2
0x1d40ec  newarr   [mscorlib]System.Object
0x1d40f1  dup
0x1d40f2  ldc.i4.0
0x1d40f3  ldarg.1
0x1d40f4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d40f9  stelem.ref
0x1d40fa  dup
0x1d40fb  ldc.i4.1
0x1d40fc  ldstr    aItem_1// "Item"
0x1d4101  stelem.ref
0x1d4102  call     string System.Windows.SR::Get(string id, object[] args)
0x1d4107  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d410c  throw
0x1d410d  ldarg.1
0x1d410e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1d4113  brtrue.s loc_1D40A6
0x1d4115  ldloc.1
0x1d4116  brtrue.s loc_1D413E
0x1d4118  ldstr    aRequiredattrib// "RequiredAttributeMissing"
0x1d411d  ldc.i4.2
0x1d411e  newarr   [mscorlib]System.Object
0x1d4123  dup
0x1d4124  ldc.i4.0
0x1d4125  ldstr    aName// "Name"
0x1d412a  stelem.ref
0x1d412b  dup
0x1d412c  ldc.i4.1
0x1d412d  ldstr    aItem_1// "Item"
0x1d4132  stelem.ref
0x1d4133  call     string System.Windows.SR::Get(string id, object[] args)
0x1d4138  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d413d  throw
0x1d413e  ldloc.2
0x1d413f  brtrue.s loc_1D4167
0x1d4141  ldstr    aRequiredattrib// "RequiredAttributeMissing"
0x1d4146  ldc.i4.2
0x1d4147  newarr   [mscorlib]System.Object
0x1d414c  dup
0x1d414d  ldc.i4.0
0x1d414e  ldstr    aValue_0// "Value"
0x1d4153  stelem.ref
0x1d4154  dup
0x1d4155  ldc.i4.1
0x1d4156  ldstr    aItem_1// "Item"
0x1d415b  stelem.ref
0x1d415c  call     string System.Windows.SR::Get(string id, object[] args)
0x1d4161  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d4166  throw
0x1d4167  ldarg.1
0x1d4168  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1d416d  pop
0x1d416e  ldloc.0
0x1d416f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> System.Windows.Annotations.ContentLocatorPart::get_NameValuePairs()
0x1d4174  ldloc.1
0x1d4175  ldloc.2
0x1d4176  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x1d417b  ldarg.1
0x1d417c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1d4181  stloc.3
0x1d4182  ldarg.1
0x1d4183  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d4188  pop
0x1d4189  ldloc.3
0x1d418a  brtrue.s loc_1D41F3
0x1d418c  ldc.i4.s 0xF
0x1d418e  ldarg.1
0x1d418f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d4194  bne.un.s loc_1D41A8
0x1d4196  ldstr    aItem_1// "Item"
0x1d419b  ldarg.1
0x1d419c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d41a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d41a6  brtrue.s loc_1D41C6
0x1d41a8  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1d41ad  ldc.i4.1
0x1d41ae  newarr   [mscorlib]System.Object
0x1d41b3  dup
0x1d41b4  ldc.i4.0
0x1d41b5  ldstr    aItem_1// "Item"
0x1d41ba  stelem.ref
0x1d41bb  call     string System.Windows.SR::Get(string id, object[] args)
0x1d41c0  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d41c5  throw
0x1d41c6  ldarg.1
0x1d41c7  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d41cc  pop
0x1d41cd  br.s     loc_1D41F3
0x1d41cf  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1d41d4  ldc.i4.1
0x1d41d5  newarr   [mscorlib]System.Object
0x1d41da  dup
0x1d41db  ldc.i4.0
0x1d41dc  ldloc.0
0x1d41dd  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d41e2  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1d41e7  stelem.ref
0x1d41e8  call     string System.Windows.SR::Get(string id, object[] args)
0x1d41ed  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d41f2  throw
0x1d41f3  ldc.i4.s 0xF
0x1d41f5  ldarg.1
0x1d41f6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d41fb  bne.un   loc_1D4076
0x1d4200  ldloc.0
0x1d4201  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d4206  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1d420b  ldarg.1
0x1d420c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d4211  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d4216  brfalse  loc_1D4076
0x1d421b  ldarg.0
0x1d421c  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorPart> System.Windows.Annotations.ContentLocator::_parts
0x1d4221  ldloc.0
0x1d4222  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocatorPart>::Add(var<u1>)
0x1d4227  ldarg.1
0x1d4228  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d422d  pop
0x1d422e  ldstr    aContentlocator_0// "ContentLocator"
0x1d4233  ldarg.1
0x1d4234  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d4239  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d423e  brfalse  loc_1D4010
0x1d4243  ldc.i4.s 0xF
0x1d4245  ldarg.1
0x1d4246  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d424b  bne.un   loc_1D4010
0x1d4250  ldarg.1
0x1d4251  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d4256  pop
0x1d4257  ret
```
