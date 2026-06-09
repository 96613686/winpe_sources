# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddPageToDocument

- ea: `0x217a0`
- end: `0x2184d`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddPageToDocument`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x218a0`

## callees

- `0x1fe10`
- `0x1fe30`
- `0x201b0`
- `0x20450`
- `0x217a0`
- `0x23af0`
- `0x23bb0`
- `0x25950`
- `0x25a70`

## string_xrefs

- `0x217ee`: `<PageContent.LinkTargets>`
- `0x2180e`: `<LinkTarget Name="{0}" />`
- `0x2183c`: `</PageContent.LinkTargets>`

## pseudocode

```c

```

## disassembly

```asm
0x217a0  ldarg.0
0x217a1  ldfld    class System.Windows.Xps.Packaging.XmlPartEditor System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_partEditor
0x217a6  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocument()
0x217ab  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentNamespace()
0x217b0  callvirt instance void System.Windows.Xps.Packaging.XmlPartEditor::PrepareXmlWriter(string startTag, string namespaceUri)
0x217b5  ldarg.0
0x217b6  ldfld    class System.Windows.Xps.Packaging.XmlPartEditor System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_partEditor
0x217bb  callvirt instance class [System.Xml]System.Xml.XmlTextWriter System.Windows.Xps.Packaging.XmlPartEditor::get_XmlWriter()
0x217c0  stloc.0
0x217c1  ldarg.0
0x217c2  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x217c7  ldarg.1
0x217c8  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x217cd  stloc.1
0x217ce  ldloc.0
0x217cf  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_PageContent()
0x217d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x217d9  ldloc.0
0x217da  call     string System.Windows.Xps.Packaging.XmlTags::get_Source()
0x217df  ldloc.1
0x217e0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x217e5  ldarg.2
0x217e6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x217eb  brfalse.s loc_21846
0x217ed  ldloc.0
0x217ee  ldstr    aPagecontentLin// "<PageContent.LinkTargets>"
0x217f3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x217f8  ldarg.2
0x217f9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x217fe  stloc.2
0x217ff  br.s     loc_21827
0x21801  ldloc.2
0x21802  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x21807  stloc.3
0x21808  ldloc.0
0x21809  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2180e  ldstr    aLinktargetName// "<LinkTarget Name=\"{0}\" />"
0x21813  ldc.i4.1
0x21814  newarr   [mscorlib]System.Object
0x21819  dup
0x2181a  ldc.i4.0
0x2181b  ldloc.3
0x2181c  stelem.ref
0x2181d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21822  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x21827  ldloc.2
0x21828  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2182d  brtrue.s loc_21801
0x2182f  leave.s  loc_2183B
0x21831  ldloc.2
0x21832  brfalse.s loc_2183A
0x21834  ldloc.2
0x21835  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2183a  endfinally
0x2183b  ldloc.0
0x2183c  ldstr    aPagecontentLin_0// "</PageContent.LinkTargets>"
0x21841  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x21846  ldloc.0
0x21847  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2184c  ret
```
