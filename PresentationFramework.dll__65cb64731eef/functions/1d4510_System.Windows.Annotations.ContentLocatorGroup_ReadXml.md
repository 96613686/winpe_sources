# System.Windows.Annotations.ContentLocatorGroup::ReadXml

- ea: `0x1d4510`
- end: `0x1d45ad`
- name: `System.Windows.Annotations.ContentLocatorGroup::ReadXml`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x38c70`
- `0x1cf6e0`
- `0x1d0910`
- `0x1d4510`
- `0x247570`

## string_xrefs

- `0x1d4513`: `reader`
- `0x1d456b`: `InvalidXmlContent`

## pseudocode

```c

```

## disassembly

```asm
0x1d4510  ldarg.1
0x1d4511  brtrue.s loc_1D451E
0x1d4513  ldstr    aReader// "reader"
0x1d4518  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d451d  throw
0x1d451e  ldarg.1
0x1d451f  ldstr    aContentlocator// "ContentLocatorGroup"
0x1d4524  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1d4529  ldarg.1
0x1d452a  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1d452f  brtrue.s loc_1D45A5
0x1d4531  ldarg.1
0x1d4532  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d4537  pop
0x1d4538  br.s     loc_1D4589
0x1d453a  ldstr    aContentlocator_0// "ContentLocator"
0x1d453f  ldarg.1
0x1d4540  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d4545  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d454a  brfalse.s loc_1D456B
0x1d454c  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_ListSerializer()
0x1d4551  ldarg.1
0x1d4552  callvirt instance object MS.Internal.Annotations.Serializer::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x1d4557  castclass System.Windows.Annotations.ContentLocator
0x1d455c  stloc.0
0x1d455d  ldarg.0
0x1d455e  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocator> System.Windows.Annotations.ContentLocatorGroup::_locators
0x1d4563  ldloc.0
0x1d4564  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocator>::Add(var<u1>)
0x1d4569  br.s     loc_1D4589
0x1d456b  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1d4570  ldc.i4.1
0x1d4571  newarr   [mscorlib]System.Object
0x1d4576  dup
0x1d4577  ldc.i4.0
0x1d4578  ldstr    aContentlocator// "ContentLocatorGroup"
0x1d457d  stelem.ref
0x1d457e  call     string System.Windows.SR::Get(string id, object[] args)
0x1d4583  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1d4588  throw
0x1d4589  ldstr    aContentlocator// "ContentLocatorGroup"
0x1d458e  ldarg.1
0x1d458f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1d4594  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d4599  brfalse.s loc_1D453A
0x1d459b  ldc.i4.s 0xF
0x1d459d  ldarg.1
0x1d459e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1d45a3  bne.un.s loc_1D453A
0x1d45a5  ldarg.1
0x1d45a6  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d45ab  pop
0x1d45ac  ret
```
