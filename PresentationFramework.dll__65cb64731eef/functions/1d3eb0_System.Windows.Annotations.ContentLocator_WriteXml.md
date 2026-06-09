# System.Windows.Annotations.ContentLocator::WriteXml

- ea: `0x1d3eb0`
- end: `0x1d3fdf`
- name: `System.Windows.Annotations.ContentLocator::WriteXml`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d3a00`
- `0x1d3a10`
- `0x1d3eb0`

## string_xrefs

- `0x1d3ece`: `xmlns`
- `0x1d3ef3`: `xmlns`
- `0x1d3eb3`: `writer`
- `0x1d3ee4`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1d3efe`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1d3ebf`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d3ed9`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d3f79`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`

## pseudocode

```c

```

## disassembly

```asm
0x1d3eb0  ldarg.1
0x1d3eb1  brtrue.s loc_1D3EBE
0x1d3eb3  ldstr    aWriter// "writer"
0x1d3eb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d3ebd  throw
0x1d3ebe  ldarg.1
0x1d3ebf  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d3ec4  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1d3ec9  stloc.0
0x1d3eca  ldloc.0
0x1d3ecb  brtrue.s loc_1D3EE3
0x1d3ecd  ldarg.1
0x1d3ece  ldstr    aXmlns// "xmlns"
0x1d3ed3  ldstr    aAnc// "anc"
0x1d3ed8  ldnull
0x1d3ed9  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d3ede  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1d3ee3  ldarg.1
0x1d3ee4  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1d3ee9  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1d3eee  stloc.0
0x1d3eef  ldloc.0
0x1d3ef0  brtrue.s loc_1D3F08
0x1d3ef2  ldarg.1
0x1d3ef3  ldstr    aXmlns// "xmlns"
0x1d3ef8  ldstr    aAnb// "anb"
0x1d3efd  ldnull
0x1d3efe  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1d3f03  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1d3f08  ldarg.0
0x1d3f09  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorPart> System.Windows.Annotations.ContentLocator::_parts
0x1d3f0e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocatorPart>::GetEnumerator()
0x1d3f13  stloc.1
0x1d3f14  br       loc_1D3FC7
0x1d3f19  ldloc.1
0x1d3f1a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Windows.Annotations.ContentLocatorPart>::get_Current()
0x1d3f1f  stloc.2
0x1d3f20  ldarg.1
0x1d3f21  ldloc.2
0x1d3f22  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d3f27  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1d3f2c  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1d3f31  stloc.0
0x1d3f32  ldloc.0
0x1d3f33  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d3f38  brfalse.s loc_1D3F40
0x1d3f3a  ldstr    aTmp// "tmp"
0x1d3f3f  stloc.0
0x1d3f40  ldarg.1
0x1d3f41  ldloc.0
0x1d3f42  ldloc.2
0x1d3f43  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d3f48  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1d3f4d  ldloc.2
0x1d3f4e  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.ContentLocatorPart::get_PartType()
0x1d3f53  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1d3f58  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1d3f5d  ldloc.2
0x1d3f5e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> System.Windows.Annotations.ContentLocatorPart::get_NameValuePairs()
0x1d3f63  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x1d3f68  stloc.3
0x1d3f69  br.s     loc_1D3FAD
0x1d3f6b  ldloc.3
0x1d3f6c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x1d3f71  stloc.s  4
0x1d3f73  ldarg.1
0x1d3f74  ldstr    aItem_1// "Item"
0x1d3f79  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d3f7e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x1d3f83  ldarg.1
0x1d3f84  ldstr    aName// "Name"
0x1d3f89  ldloca.s 4
0x1d3f8b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1d3f90  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d3f95  ldarg.1
0x1d3f96  ldstr    aValue_0// "Value"
0x1d3f9b  ldloca.s 4
0x1d3f9d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x1d3fa2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d3fa7  ldarg.1
0x1d3fa8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d3fad  ldloc.3
0x1d3fae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d3fb3  brtrue.s loc_1D3F6B
0x1d3fb5  leave.s  loc_1D3FC1
0x1d3fb7  ldloc.3
0x1d3fb8  brfalse.s loc_1D3FC0
0x1d3fba  ldloc.3
0x1d3fbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d3fc0  endfinally
0x1d3fc1  ldarg.1
0x1d3fc2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d3fc7  ldloc.1
0x1d3fc8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d3fcd  brtrue   loc_1D3F19
0x1d3fd2  leave.s  loc_1D3FDE
0x1d3fd4  ldloc.1
0x1d3fd5  brfalse.s loc_1D3FDD
0x1d3fd7  ldloc.1
0x1d3fd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d3fdd  endfinally
0x1d3fde  ret
```
