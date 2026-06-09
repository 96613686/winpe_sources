# System.Windows.Annotations.AnnotationResource::WriteXml

- ea: `0x1d0630`
- end: `0x1d0727`
- name: `System.Windows.Annotations.AnnotationResource::WriteXml`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d0630`
- `0x1d0910`
- `0x1d09c0`
- `0x247520`

## string_xrefs

- `0x1d0651`: `xmlns`
- `0x1d0633`: `writer`
- `0x1d063f`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d065c`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`

## pseudocode

```c

```

## disassembly

```asm
0x1d0630  ldarg.1
0x1d0631  brtrue.s loc_1D063E
0x1d0633  ldstr    aWriter// "writer"
0x1d0638  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d063d  throw
0x1d063e  ldarg.1
0x1d063f  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d0644  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1d0649  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d064e  brfalse.s loc_1D0666
0x1d0650  ldarg.1
0x1d0651  ldstr    aXmlns// "xmlns"
0x1d0656  ldstr    aAnc// "anc"
0x1d065b  ldnull
0x1d065c  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d0661  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1d0666  ldarg.1
0x1d0667  ldstr    aId_2// "Id"
0x1d066c  ldarg.0
0x1d066d  ldfld    valuetype [mscorlib]System.Guid System.Windows.Annotations.AnnotationResource::_id
0x1d0672  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x1d0677  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d067c  ldarg.0
0x1d067d  ldfld    string System.Windows.Annotations.AnnotationResource::_name
0x1d0682  brfalse.s loc_1D0695
0x1d0684  ldarg.1
0x1d0685  ldstr    aName// "Name"
0x1d068a  ldarg.0
0x1d068b  ldfld    string System.Windows.Annotations.AnnotationResource::_name
0x1d0690  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d0695  ldarg.0
0x1d0696  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorBase> System.Windows.Annotations.AnnotationResource::_locators
0x1d069b  brfalse.s loc_1D06EB
0x1d069d  ldarg.0
0x1d069e  ldfld    class MS.Internal.Annotations.AnnotationObservableCollection`1<class System.Windows.Annotations.ContentLocatorBase> System.Windows.Annotations.AnnotationResource::_locators
0x1d06a3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.ContentLocatorBase>::GetEnumerator()
0x1d06a8  stloc.0
0x1d06a9  br.s     loc_1D06D7
0x1d06ab  ldloc.0
0x1d06ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Windows.Annotations.ContentLocatorBase>::get_Current()
0x1d06b1  stloc.1
0x1d06b2  ldloc.1
0x1d06b3  brfalse.s loc_1D06D7
0x1d06b5  ldloc.1
0x1d06b6  isinst   System.Windows.Annotations.ContentLocatorGroup
0x1d06bb  brfalse.s loc_1D06CB
0x1d06bd  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_LocatorGroupSerializer()
0x1d06c2  ldarg.1
0x1d06c3  ldloc.1
0x1d06c4  callvirt instance void MS.Internal.Annotations.Serializer::Serialize(class [System.Xml]System.Xml.XmlWriter writer, object obj)
0x1d06c9  br.s     loc_1D06D7
0x1d06cb  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.AnnotationResource::get_ListSerializer()
0x1d06d0  ldarg.1
0x1d06d1  ldloc.1
0x1d06d2  callvirt instance void MS.Internal.Annotations.Serializer::Serialize(class [System.Xml]System.Xml.XmlWriter writer, object obj)
0x1d06d7  ldloc.0
0x1d06d8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d06dd  brtrue.s loc_1D06AB
0x1d06df  leave.s  loc_1D06EB
0x1d06e1  ldloc.0
0x1d06e2  brfalse.s loc_1D06EA
0x1d06e4  ldloc.0
0x1d06e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d06ea  endfinally
0x1d06eb  ldarg.0
0x1d06ec  ldfld    class MS.Internal.Annotations.XmlElementCollection System.Windows.Annotations.AnnotationResource::_contents
0x1d06f1  brfalse.s loc_1D0726
0x1d06f3  ldarg.0
0x1d06f4  ldfld    class MS.Internal.Annotations.XmlElementCollection System.Windows.Annotations.AnnotationResource::_contents
0x1d06f9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::GetEnumerator()
0x1d06fe  stloc.2
0x1d06ff  br.s     loc_1D0712
0x1d0701  ldloc.2
0x1d0702  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlElement>::get_Current()
0x1d0707  stloc.3
0x1d0708  ldloc.3
0x1d0709  brfalse.s loc_1D0712
0x1d070b  ldloc.3
0x1d070c  ldarg.1
0x1d070d  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x1d0712  ldloc.2
0x1d0713  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d0718  brtrue.s loc_1D0701
0x1d071a  leave.s  loc_1D0726
0x1d071c  ldloc.2
0x1d071d  brfalse.s loc_1D0725
0x1d071f  ldloc.2
0x1d0720  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d0725  endfinally
0x1d0726  ret
```
