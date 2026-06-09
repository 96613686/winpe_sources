# System.Windows.Annotations.ContentLocatorGroup::WriteXml

- ea: `0x1d44a0`
- end: `0x1d450c`
- name: `System.Windows.Annotations.ContentLocatorGroup::WriteXml`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d0910`
- `0x1d44a0`
- `0x247520`

## string_xrefs

- `0x1d44be`: `xmlns`
- `0x1d44a3`: `writer`
- `0x1d44af`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d44c9`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`

## pseudocode

```c

```

## disassembly

```asm
0x1d44a0  ldarg.1
0x1d44a1  brtrue.s loc_1D44AE
0x1d44a3  ldstr    aWriter// "writer"
0x1d44a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d44ad  throw
0x1d44ae  ldarg.1
0x1d44af  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d44b4  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1d44b9  stloc.0
0x1d44ba  ldloc.0
0x1d44bb  brtrue.s loc_1D44D3
0x1d44bd  ldarg.1
0x1d44be  ldstr    aXmlns// "xmlns"
0x1d44c3  ldstr    aAnc// "anc"
0x1d44c8  ldnull
0x1d44c9  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d44ce  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1d44d3  ldarg.0
0x1d44d4  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocator> System.Windows.Annotations.ContentLocatorGroup::_locators
0x1d44d9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocator>::GetEnumerator()
0x1d44de  stloc.1
0x1d44df  br.s     loc_1D44F7
0x1d44e1  ldloc.1
0x1d44e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Windows.Annotations.ContentLocator>::get_Current()
0x1d44e7  stloc.2
0x1d44e8  ldloc.2
0x1d44e9  brfalse.s loc_1D44F7
0x1d44eb  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_ListSerializer()
0x1d44f0  ldarg.1
0x1d44f1  ldloc.2
0x1d44f2  callvirt instance void MS.Internal.Annotations.Serializer::Serialize(class [System.Xml]System.Xml.XmlWriter writer, object obj)
0x1d44f7  ldloc.1
0x1d44f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d44fd  brtrue.s loc_1D44E1
0x1d44ff  leave.s  loc_1D450B
0x1d4501  ldloc.1
0x1d4502  brfalse.s loc_1D450A
0x1d4504  ldloc.1
0x1d4505  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d450a  endfinally
0x1d450b  ret
```
