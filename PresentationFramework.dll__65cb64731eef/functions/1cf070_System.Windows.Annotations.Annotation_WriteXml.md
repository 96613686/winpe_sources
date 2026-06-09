# System.Windows.Annotations.Annotation::WriteXml

- ea: `0x1cf070`
- end: `0x1cf2b5`
- name: `System.Windows.Annotations.Annotation::WriteXml`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38c40`
- `0x1cf070`
- `0x1cf740`
- `0x247520`

## string_xrefs

- `0x1cf09d`: `xmlns`
- `0x1cf0c5`: `xmlns`
- `0x1cf073`: `writer`
- `0x1cf0b3`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1cf0d0`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1cf1b0`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1cf08b`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1cf0a8`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1cf183`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1cf1f1`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1cf255`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`

## pseudocode

```c

```

## disassembly

```asm
0x1cf070  ldarg.1
0x1cf071  brtrue.s loc_1CF07E
0x1cf073  ldstr    aWriter// "writer"
0x1cf078  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cf07d  throw
0x1cf07e  ldc.i4.s 0x10
0x1cf080  ldc.i4   0xBCF
0x1cf085  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1cf08a  ldarg.1
0x1cf08b  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1cf090  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1cf095  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cf09a  brfalse.s loc_1CF0B2
0x1cf09c  ldarg.1
0x1cf09d  ldstr    aXmlns// "xmlns"
0x1cf0a2  ldstr    aAnc// "anc"
0x1cf0a7  ldnull
0x1cf0a8  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1cf0ad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1cf0b2  ldarg.1
0x1cf0b3  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1cf0b8  callvirt instance string [System.Xml]System.Xml.XmlWriter::LookupPrefix(string)
0x1cf0bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1cf0c2  brfalse.s loc_1CF0DA
0x1cf0c4  ldarg.1
0x1cf0c5  ldstr    aXmlns// "xmlns"
0x1cf0ca  ldstr    aAnb// "anb"
0x1cf0cf  ldnull
0x1cf0d0  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1cf0d5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1cf0da  ldarg.0
0x1cf0db  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.Annotation::_typeName
0x1cf0e0  ldnull
0x1cf0e1  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1cf0e6  brfalse.s loc_1CF0F8
0x1cf0e8  ldstr    aCannotserializ// "CannotSerializeInvalidInstance"
0x1cf0ed  call     string System.Windows.SR::Get(string id)
0x1cf0f2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1cf0f7  throw
0x1cf0f8  ldarg.1
0x1cf0f9  ldstr    aId_2// "Id"
0x1cf0fe  ldarg.0
0x1cf0ff  ldfld    valuetype [mscorlib]System.Guid System.Windows.Annotations.Annotation::_id
0x1cf104  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x1cf109  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cf10e  ldarg.1
0x1cf10f  ldstr    aCreationtime// "CreationTime"
0x1cf114  ldarg.0
0x1cf115  ldfld    valuetype [mscorlib]System.DateTime System.Windows.Annotations.Annotation::_created
0x1cf11a  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime)
0x1cf11f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cf124  ldarg.1
0x1cf125  ldstr    aLastmodificati_0// "LastModificationTime"
0x1cf12a  ldarg.0
0x1cf12b  ldfld    valuetype [mscorlib]System.DateTime System.Windows.Annotations.Annotation::_modified
0x1cf130  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime)
0x1cf135  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1cf13a  ldarg.1
0x1cf13b  ldstr    aType_3// "Type"
0x1cf140  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string)
0x1cf145  ldarg.1
0x1cf146  ldarg.0
0x1cf147  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.Annotation::_typeName
0x1cf14c  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1cf151  ldarg.0
0x1cf152  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Windows.Annotations.Annotation::_typeName
0x1cf157  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1cf15c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteQualifiedName(string, string)
0x1cf161  ldarg.1
0x1cf162  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0x1cf167  ldarg.0
0x1cf168  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<string> System.Windows.Annotations.Annotation::_authors
0x1cf16d  brfalse.s loc_1CF1D5
0x1cf16f  ldarg.0
0x1cf170  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<string> System.Windows.Annotations.Annotation::_authors
0x1cf175  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Count()
0x1cf17a  ldc.i4.0
0x1cf17b  ble.s    loc_1CF1D5
0x1cf17d  ldarg.1
0x1cf17e  ldstr    aAuthors// "Authors"
0x1cf183  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1cf188  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x1cf18d  ldarg.0
0x1cf18e  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<string> System.Windows.Annotations.Annotation::_authors
0x1cf193  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::GetEnumerator()
0x1cf198  stloc.0
0x1cf199  br.s     loc_1CF1BB
0x1cf19b  ldloc.0
0x1cf19c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1cf1a1  stloc.1
0x1cf1a2  ldloc.1
0x1cf1a3  brfalse.s loc_1CF1BB
0x1cf1a5  ldarg.1
0x1cf1a6  ldstr    aAnb// "anb"
0x1cf1ab  ldstr    aStringauthor// "StringAuthor"
0x1cf1b0  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1cf1b5  ldloc.1
0x1cf1b6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string, string)
0x1cf1bb  ldloc.0
0x1cf1bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1cf1c1  brtrue.s loc_1CF19B
0x1cf1c3  leave.s  loc_1CF1CF
0x1cf1c5  ldloc.0
0x1cf1c6  brfalse.s loc_1CF1CE
0x1cf1c8  ldloc.0
0x1cf1c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cf1ce  endfinally
0x1cf1cf  ldarg.1
0x1cf1d0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1cf1d5  ldarg.0
0x1cf1d6  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_anchors
0x1cf1db  brfalse.s loc_1CF239
0x1cf1dd  ldarg.0
0x1cf1de  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_anchors
0x1cf1e3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::get_Count()
0x1cf1e8  ldc.i4.0
0x1cf1e9  ble.s    loc_1CF239
0x1cf1eb  ldarg.1
0x1cf1ec  ldstr    aAnchors// "Anchors"
0x1cf1f1  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1cf1f6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x1cf1fb  ldarg.0
0x1cf1fc  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_anchors
0x1cf201  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::GetEnumerator()
0x1cf206  stloc.2
0x1cf207  br.s     loc_1CF21F
0x1cf209  ldloc.2
0x1cf20a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Windows.Annotations.AnnotationResource>::get_Current()
0x1cf20f  stloc.3
0x1cf210  ldloc.3
0x1cf211  brfalse.s loc_1CF21F
0x1cf213  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.Annotation::get_ResourceSerializer()
0x1cf218  ldarg.1
0x1cf219  ldloc.3
0x1cf21a  callvirt instance void MS.Internal.Annotations.Serializer::Serialize(class [System.Xml]System.Xml.XmlWriter writer, object obj)
0x1cf21f  ldloc.2
0x1cf220  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1cf225  brtrue.s loc_1CF209
0x1cf227  leave.s  loc_1CF233
0x1cf229  ldloc.2
0x1cf22a  brfalse.s loc_1CF232
0x1cf22c  ldloc.2
0x1cf22d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cf232  endfinally
0x1cf233  ldarg.1
0x1cf234  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1cf239  ldarg.0
0x1cf23a  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_cargos
0x1cf23f  brfalse.s loc_1CF2A5
0x1cf241  ldarg.0
0x1cf242  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_cargos
0x1cf247  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::get_Count()
0x1cf24c  ldc.i4.0
0x1cf24d  ble.s    loc_1CF2A5
0x1cf24f  ldarg.1
0x1cf250  ldstr    aCargos// "Cargos"
0x1cf255  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1cf25a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x1cf25f  ldarg.0
0x1cf260  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_cargos
0x1cf265  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::GetEnumerator()
0x1cf26a  stloc.s  4
0x1cf26c  br.s     loc_1CF288
0x1cf26e  ldloc.s  4
0x1cf270  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Windows.Annotations.AnnotationResource>::get_Current()
0x1cf275  stloc.s  5
0x1cf277  ldloc.s  5
0x1cf279  brfalse.s loc_1CF288
0x1cf27b  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.Annotation::get_ResourceSerializer()
0x1cf280  ldarg.1
0x1cf281  ldloc.s  5
0x1cf283  callvirt instance void MS.Internal.Annotations.Serializer::Serialize(class [System.Xml]System.Xml.XmlWriter writer, object obj)
0x1cf288  ldloc.s  4
0x1cf28a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1cf28f  brtrue.s loc_1CF26E
0x1cf291  leave.s  loc_1CF29F
0x1cf293  ldloc.s  4
0x1cf295  brfalse.s loc_1CF29E
0x1cf297  ldloc.s  4
0x1cf299  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cf29e  endfinally
0x1cf29f  ldarg.1
0x1cf2a0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1cf2a5  leave.s  loc_1CF2B4
0x1cf2a7  ldc.i4.s 0x10
0x1cf2a9  ldc.i4   0xBD0
0x1cf2ae  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1cf2b3  endfinally
0x1cf2b4  ret
```
