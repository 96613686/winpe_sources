# System.Windows.Annotations.AnnotationResource::ReadXml

- ea: `0x1d0730`
- end: `0x1d0830`
- name: `System.Windows.Annotations.AnnotationResource::ReadXml`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x38c70`
- `0x1d0730`
- `0x1d0910`
- `0x1d0940`
- `0x1d0980`
- `0x1d09c0`
- `0x1d09f0`
- `0x247570`

## string_xrefs

- `0x1d0733`: `reader`
- `0x1d07e8`: `InvalidXmlContent`

## pseudocode

```c

```

## disassembly

```asm
0x1d0730  ldarg.1
0x1d0731  brtrue.s loc_1D073E
0x1d0733  ldstr    aReader// "reader"
0x1d0738  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d073d  throw
0x1d073e  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1d0743  stloc.0
0x1d0744  ldarg.0
0x1d0745  ldarg.1
0x1d0746  call     instance void System.Windows.Annotations.AnnotationResource::ReadAttributes(class [System.Xml]System.Xml.XmlReader reader)
0x1d074b  ldarg.1
0x1d074c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1d0751  brtrue   loc_1D0828
0x1d0756  ldarg.1
0x1d0757  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d075c  pop
0x1d075d  br       loc_1D0806
0x1d0762  ldstr    aContentlocator// "ContentLocatorGroup"
0x1d0767  ldarg.1
0x1d0768  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d076d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d0772  brfalse.s loc_1D0793
0x1d0774  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_LocatorGroupSerializer()
0x1d0779  ldarg.1
0x1d077a  callvirt instance object MS.Internal.Annotations.Serializer::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x1d077f  castclass System.Windows.Annotations.ContentLocatorBase
0x1d0784  stloc.1
0x1d0785  ldarg.0
0x1d0786  call     instance class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorBase> System.Windows.Annotations.AnnotationResource::get_InternalLocators()
0x1d078b  ldloc.1
0x1d078c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocatorBase>::Add(var<u1>)
0x1d0791  br.s     loc_1D0806
0x1d0793  ldstr    aContentlocator_0// "ContentLocator"
0x1d0798  ldarg.1
0x1d0799  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d079e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d07a3  brfalse.s loc_1D07C4
0x1d07a5  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_ListSerializer()
0x1d07aa  ldarg.1
0x1d07ab  callvirt instance object MS.Internal.Annotations.Serializer::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x1d07b0  castclass System.Windows.Annotations.ContentLocatorBase
0x1d07b5  stloc.2
0x1d07b6  ldarg.0
0x1d07b7  call     instance class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorBase> System.Windows.Annotations.AnnotationResource::get_InternalLocators()
0x1d07bc  ldloc.2
0x1d07bd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocatorBase>::Add(var<u1>)
0x1d07c2  br.s     loc_1D0806
0x1d07c4  ldc.i4.1
0x1d07c5  ldarg.1
0x1d07c6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d07cb  bne.un.s loc_1D07E8
0x1d07cd  ldloc.0
0x1d07ce  ldarg.1
0x1d07cf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ReadNode(class [System.Xml]System.Xml.XmlReader)
0x1d07d4  isinst   [System.Xml]System.Xml.XmlElement
0x1d07d9  stloc.3
0x1d07da  ldarg.0
0x1d07db  call     instance class MS.Internal.Annotations.XmlElementCollection System.Windows.Annotations.AnnotationResource::get_InternalContents()
0x1d07e0  ldloc.3
0x1d07e1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Add(var<u1>)
0x1d07e6  br.s     loc_1D0806
0x1d07e8  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1d07ed  ldc.i4.1
0x1d07ee  newarr   [mscorlib]System.Object
0x1d07f3  dup
0x1d07f4  ldc.i4.0
0x1d07f5  ldstr    aResource// "Resource"
0x1d07fa  stelem.ref
0x1d07fb  call     string System.Windows.SR::Get(string id, object[] args)
0x1d0800  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d0805  throw
0x1d0806  ldstr    aResource// "Resource"
0x1d080b  ldarg.1
0x1d080c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d0811  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d0816  brfalse  loc_1D0762
0x1d081b  ldc.i4.s 0xF
0x1d081d  ldarg.1
0x1d081e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d0823  bne.un   loc_1D0762
0x1d0828  ldarg.1
0x1d0829  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d082e  pop
0x1d082f  ret
```
