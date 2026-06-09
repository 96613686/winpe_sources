# Microsoft.ReportingServices.Library.Presentation::AddSlidesToPresentation

- ea: `0x32870`
- end: `0x3298c`
- name: `Microsoft.ReportingServices.Library.Presentation::AddSlidesToPresentation`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x331a0`

## callees

- `0x32870`

## string_xrefs

- `0x32870`: `/ppt/presentation.xml`
- `0x328ce`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/slide`
- `0x328e0`: `http://schemas.openxmlformats.org/presentationml/2006/main`
- `0x328f2`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`

## pseudocode

```c

```

## disassembly

```asm
0x32870  ldstr    aPptPresentatio// "/ppt/presentation.xml"
0x32875  ldc.i4.2
0x32876  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x3287b  stloc.0
0x3287c  ldarg.0
0x3287d  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.Library.Presentation::m_pptx
0x32882  ldloc.0
0x32883  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x32888  stloc.1
0x32889  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x3288e  stloc.2
0x3288f  ldloc.2
0x32890  ldloc.1
0x32891  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x32896  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [mscorlib]System.IO.Stream)
0x3289b  ldloc.2
0x3289c  ldstr    aPSldidlst// "p:sldIdLst"
0x328a1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x328a6  ldc.i4.0
0x328a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x328ac  stloc.3
0x328ad  ldc.i4   0x101
0x328b2  stloc.s  4
0x328b4  ldarg.1
0x328b5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::GetEnumerator()
0x328ba  stloc.s  5
0x328bc  br       loc_32963
0x328c1  ldloca.s 5
0x328c3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Uri>::get_Current()
0x328c8  stloc.s  6
0x328ca  ldloc.1
0x328cb  ldloc.s  6
0x328cd  ldc.i4.0
0x328ce  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/offic"...
0x328d3  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x328d8  stloc.s  7
0x328da  ldloc.2
0x328db  ldstr    aPSldid// "p:sldId"
0x328e0  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/prese"...
0x328e5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x328ea  stloc.s  8
0x328ec  ldloc.2
0x328ed  ldstr    aRId// "r:id"
0x328f2  ldstr    aHttpSchemasOpe_1// "http://schemas.openxmlformats.org/offic"...
0x328f7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0x328fc  stloc.s  9
0x328fe  ldloc.s  9
0x32900  ldloc.s  7
0x32902  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_Id()
0x32907  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3290c  ldloc.2
0x3290d  ldstr    aId_3// "id"
0x32912  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x32917  stloc.s  0xA
0x32919  ldloc.s  0xA
0x3291b  ldc.i4   0x100
0x32920  ldloc.s  4
0x32922  add
0x32923  stloc.s  0xB
0x32925  ldloca.s 0xB
0x32927  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3292c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x32931  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x32936  ldloc.s  8
0x32938  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3293d  ldloc.s  9
0x3293f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x32944  pop
0x32945  ldloc.s  8
0x32947  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3294c  ldloc.s  0xA
0x3294e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x32953  pop
0x32954  ldloc.3
0x32955  ldloc.s  8
0x32957  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3295c  pop
0x3295d  ldloc.s  4
0x3295f  ldc.i4.1
0x32960  add
0x32961  stloc.s  4
0x32963  ldloca.s 5
0x32965  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Uri>::MoveNext()
0x3296a  brtrue   loc_328C1
0x3296f  leave.s  loc_3297F
0x32971  ldloca.s 5
0x32973  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Uri>
0x32979  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3297e  endfinally
0x3297f  ldloc.2
0x32980  ldloc.1
0x32981  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x32986  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(class [mscorlib]System.IO.Stream)
0x3298b  ret
```
