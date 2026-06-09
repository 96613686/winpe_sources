# System.Windows.Annotations.Storage.XmlStreamStore::LoadStream

- ea: `0x1d5400`
- end: `0x1d54fd`
- name: `System.Windows.Annotations.Storage.XmlStreamStore::LoadStream`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d59b0`

## callees

- `0x1d4ae0`
- `0x1d5400`
- `0x1d5500`
- `0x1d5670`

## string_xrefs

- `0x1d54a2`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1d548d`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`
- `0x1d5442`: `<?xml version="1.0" encoding="utf-8"?> <anc:Annotations xmlns:anc="http://schemas.microsoft.com/windows/annotations/2003/11/core" xmlns:anb="http://schemas.microsoft.com/windows/annotations/2003/11/base" />`

## pseudocode

```c

```

## disassembly

```asm
0x1d5400  ldarg.0
0x1d5401  ldarg.1
0x1d5402  call     instance void System.Windows.Annotations.Storage.XmlStreamStore::CheckKnownNamespaces(class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> knownNamespaces)
0x1d5407  ldarg.0
0x1d5408  call     instance object System.Windows.Annotations.Storage.AnnotationStore::get_SyncRoot()
0x1d540d  stloc.0
0x1d540e  ldc.i4.0
0x1d540f  stloc.1
0x1d5410  ldloc.0
0x1d5411  ldloca.s 1
0x1d5413  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1d5418  ldarg.0
0x1d5419  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1d541e  stfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d5423  ldarg.0
0x1d5424  ldfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d5429  ldc.i4.0
0x1d542a  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x1d542f  ldarg.0
0x1d5430  ldfld    class [mscorlib]System.IO.Stream System.Windows.Annotations.Storage.XmlStreamStore::_stream
0x1d5435  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1d543a  brtrue.s loc_1D544E
0x1d543c  ldarg.0
0x1d543d  ldfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d5442  ldstr    aXmlVersion10En// "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1d5447  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x1d544c  br.s     loc_1D546C
0x1d544e  ldarg.0
0x1d544f  ldarg.0
0x1d5450  ldarg.1
0x1d5451  call     instance class [WindowsBase]System.Windows.Markup.XmlCompatibilityReader System.Windows.Annotations.Storage.XmlStreamStore::SetupReader(class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> knownNamespaces)
0x1d5456  stfld    class [WindowsBase]System.Windows.Markup.XmlCompatibilityReader System.Windows.Annotations.Storage.XmlStreamStore::_xmlCompatibilityReader
0x1d545b  ldarg.0
0x1d545c  ldfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d5461  ldarg.0
0x1d5462  ldfld    class [WindowsBase]System.Windows.Markup.XmlCompatibilityReader System.Windows.Annotations.Storage.XmlStreamStore::_xmlCompatibilityReader
0x1d5467  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x1d546c  ldarg.0
0x1d546d  ldarg.0
0x1d546e  ldfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d5473  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x1d5478  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x1d547d  stfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Windows.Annotations.Storage.XmlStreamStore::_namespaceManager
0x1d5482  ldarg.0
0x1d5483  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Windows.Annotations.Storage.XmlStreamStore::_namespaceManager
0x1d5488  ldstr    aAnc// "anc"
0x1d548d  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d5492  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1d5497  ldarg.0
0x1d5498  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Windows.Annotations.Storage.XmlStreamStore::_namespaceManager
0x1d549d  ldstr    aAnb// "anb"
0x1d54a2  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1d54a7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1d54ac  ldarg.0
0x1d54ad  ldfld    class [System.Xml]System.Xml.XmlDocument System.Windows.Annotations.Storage.XmlStreamStore::_document
0x1d54b2  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x1d54b7  stloc.2
0x1d54b8  ldloc.2
0x1d54b9  ldstr    aAncAnnotations// "//anc:Annotations"
0x1d54be  ldarg.0
0x1d54bf  ldfld    class [System.Xml]System.Xml.XmlNamespaceManager System.Windows.Annotations.Storage.XmlStreamStore::_namespaceManager
0x1d54c4  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0x1d54c9  stloc.3
0x1d54ca  ldloc.3
0x1d54cb  callvirt instance int32 [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Count()
0x1d54d0  ldc.i4.1
0x1d54d1  ceq
0x1d54d3  ldstr    aMoreThanOneAnn// "More than one annotation returned for t"...
0x1d54d8  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1d54dd  ldloc.3
0x1d54de  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x1d54e3  pop
0x1d54e4  ldarg.0
0x1d54e5  ldloc.3
0x1d54e6  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x1d54eb  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Windows.Annotations.Storage.XmlStreamStore::_rootNavigator
0x1d54f0  leave.s  loc_1D54FC
0x1d54f2  ldloc.1
0x1d54f3  brfalse.s loc_1D54FB
0x1d54f5  ldloc.0
0x1d54f6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1d54fb  endfinally
0x1d54fc  ret
```
