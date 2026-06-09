# System.Xml.Xsl.XsltOld.OutKeywords::.ctor

- ea: `0xbb00`
- end: `0xbb7e`
- name: `System.Xml.Xsl.XsltOld.OutKeywords::.ctor`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0xdea0`

## string_xrefs

- `0xbb3b`: `xmlns`
- `0xbb6e`: `http://www.w3.org/2000/xmlns/`
- `0xbb5d`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0xbb00  ldarg.0
0xbb01  call     instance void [mscorlib]System.Object::.ctor()
0xbb06  ldarg.0
0xbb07  ldarg.1
0xbb08  ldsfld   string [mscorlib]System.String::Empty
0xbb0d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb12  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomEmpty
0xbb17  ldarg.0
0xbb18  ldarg.1
0xbb19  ldstr    aLang// "lang"
0xbb1e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb23  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomLang
0xbb28  ldarg.0
0xbb29  ldarg.1
0xbb2a  ldstr    aSpace// "space"
0xbb2f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb34  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomSpace
0xbb39  ldarg.0
0xbb3a  ldarg.1
0xbb3b  ldstr    aXmlns// "xmlns"
0xbb40  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb45  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomXmlns
0xbb4a  ldarg.0
0xbb4b  ldarg.1
0xbb4c  ldstr    aXml// "xml"
0xbb51  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb56  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomXml
0xbb5b  ldarg.0
0xbb5c  ldarg.1
0xbb5d  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xbb62  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb67  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomXmlNamespace
0xbb6c  ldarg.0
0xbb6d  ldarg.1
0xbb6e  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0xbb73  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xbb78  stfld    string System.Xml.Xsl.XsltOld.OutKeywords::_AtomXmlnsNamespace
0xbb7d  ret
```
