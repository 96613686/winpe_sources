# System.Xml.XmlDocument::.ctor_1

- ea: `0x4adb0`
- end: `0x4af03`
- name: `System.Xml.XmlDocument::.ctor_1`
- size: `339`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ad90`
- `0x4ada0`
- `0x4f3a0`

## callees

- `0x13200`
- `0x49320`
- `0x4bd20`
- `0x50ff0`

## string_xrefs

- `0x4aecc`: `http://www.w3.org/XML/1998/namespace`
- `0x4aebb`: `http://www.w3.org/2000/xmlns/`
- `0x4ae77`: `xmlns`
- `0x4ae00`: `#comment`

## pseudocode

```c

```

## disassembly

```asm
0x4adb0  ldarg.0
0x4adb1  call     instance void System.Xml.XmlNode::.ctor()
0x4adb6  ldarg.0
0x4adb7  ldarg.1
0x4adb8  stfld    class System.Xml.XmlImplementation System.Xml.XmlDocument::implementation
0x4adbd  ldarg.0
0x4adbe  ldarg.0
0x4adbf  newobj   instance void System.Xml.DomNameTable::.ctor(class System.Xml.XmlDocument document)
0x4adc4  stfld    class System.Xml.DomNameTable System.Xml.XmlDocument::domNameTable
0x4adc9  ldarg.0
0x4adca  call     instance class System.Xml.XmlNameTable System.Xml.XmlDocument::get_NameTable()
0x4adcf  stloc.0
0x4add0  ldloc.0
0x4add1  ldsfld   string [mscorlib]System.String::Empty
0x4add6  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4addb  pop
0x4addc  ldarg.0
0x4addd  ldloc.0
0x4adde  ldstr    aDocument_0// "#document"
0x4ade3  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ade8  stfld    string System.Xml.XmlDocument::strDocumentName
0x4aded  ldarg.0
0x4adee  ldloc.0
0x4adef  ldstr    aDocumentFragme// "#document-fragment"
0x4adf4  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4adf9  stfld    string System.Xml.XmlDocument::strDocumentFragmentName
0x4adfe  ldarg.0
0x4adff  ldloc.0
0x4ae00  ldstr    aComment_1// "#comment"
0x4ae05  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae0a  stfld    string System.Xml.XmlDocument::strCommentName
0x4ae0f  ldarg.0
0x4ae10  ldloc.0
0x4ae11  ldstr    aText_1// "#text"
0x4ae16  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae1b  stfld    string System.Xml.XmlDocument::strTextName
0x4ae20  ldarg.0
0x4ae21  ldloc.0
0x4ae22  ldstr    aCdataSection// "#cdata-section"
0x4ae27  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae2c  stfld    string System.Xml.XmlDocument::strCDataSectionName
0x4ae31  ldarg.0
0x4ae32  ldloc.0
0x4ae33  ldstr    aEntity// "#entity"
0x4ae38  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae3d  stfld    string System.Xml.XmlDocument::strEntityName
0x4ae42  ldarg.0
0x4ae43  ldloc.0
0x4ae44  ldstr    aId// "id"
0x4ae49  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae4e  stfld    string System.Xml.XmlDocument::strID
0x4ae53  ldarg.0
0x4ae54  ldloc.0
0x4ae55  ldstr    aWhitespace_0// "#whitespace"
0x4ae5a  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae5f  stfld    string System.Xml.XmlDocument::strNonSignificantWhitespaceName
0x4ae64  ldarg.0
0x4ae65  ldloc.0
0x4ae66  ldstr    aSignificantWhi// "#significant-whitespace"
0x4ae6b  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae70  stfld    string System.Xml.XmlDocument::strSignificantWhitespaceName
0x4ae75  ldarg.0
0x4ae76  ldloc.0
0x4ae77  ldstr    aXmlns// "xmlns"
0x4ae7c  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae81  stfld    string System.Xml.XmlDocument::strXmlns
0x4ae86  ldarg.0
0x4ae87  ldloc.0
0x4ae88  ldstr    aXml// "xml"
0x4ae8d  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4ae92  stfld    string System.Xml.XmlDocument::strXml
0x4ae97  ldarg.0
0x4ae98  ldloc.0
0x4ae99  ldstr    aSpace// "space"
0x4ae9e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4aea3  stfld    string System.Xml.XmlDocument::strSpace
0x4aea8  ldarg.0
0x4aea9  ldloc.0
0x4aeaa  ldstr    aLang// "lang"
0x4aeaf  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4aeb4  stfld    string System.Xml.XmlDocument::strLang
0x4aeb9  ldarg.0
0x4aeba  ldloc.0
0x4aebb  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x4aec0  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4aec5  stfld    string System.Xml.XmlDocument::strReservedXmlns
0x4aeca  ldarg.0
0x4aecb  ldloc.0
0x4aecc  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x4aed1  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4aed6  stfld    string System.Xml.XmlDocument::strReservedXml
0x4aedb  ldarg.0
0x4aedc  ldloc.0
0x4aedd  ldsfld   string [mscorlib]System.String::Empty
0x4aee2  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x4aee7  stfld    string System.Xml.XmlDocument::strEmpty
0x4aeec  ldarg.0
0x4aeed  ldsfld   string [mscorlib]System.String::Empty
0x4aef2  stfld    string System.Xml.XmlDocument::baseURI
0x4aef7  ldarg.0
0x4aef8  newobj   instance void [mscorlib]System.Object::.ctor()
0x4aefd  stfld    object System.Xml.XmlDocument::objLock
0x4af02  ret
```
