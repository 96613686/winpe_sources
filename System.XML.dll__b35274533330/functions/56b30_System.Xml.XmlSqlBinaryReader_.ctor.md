# System.Xml.XmlSqlBinaryReader::.ctor

- ea: `0x56b30`
- end: `0x56d98`
- name: `System.Xml.XmlSqlBinaryReader::.ctor`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x22eb0`

## callees

- `0xe390`
- `0xef20`
- `0x13200`
- `0x17930`
- `0x23400`
- `0x234b0`
- `0x235b0`
- `0x235f0`
- `0x236a0`
- `0x236d0`
- `0x23700`
- `0x23760`
- `0x56b30`
- `0x585c0`
- `0x5a480`
- `0x119210`
- `0x119540`

## string_xrefs

- `0x56c61`: `http://www.w3.org/XML/1998/namespace`
- `0x56baf`: `http://www.w3.org/2000/xmlns/`
- `0x56b99`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x56b30  ldarg.0
0x56b31  call     instance void System.Xml.XmlReader::.ctor()
0x56b36  ldarg.0
0x56b37  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x56b3c  stfld    class [mscorlib]System.Text.Encoding System.Xml.XmlSqlBinaryReader::unicode
0x56b41  ldarg.0
0x56b42  call     valuetype System.Xml.XmlCharType System.Xml.XmlCharType::get_Instance()
0x56b47  stfld    valuetype System.Xml.XmlCharType System.Xml.XmlSqlBinaryReader::xmlCharType
0x56b4c  ldarg.0
0x56b4d  ldarg.s  6
0x56b4f  callvirt instance class System.Xml.XmlNameTable System.Xml.XmlReaderSettings::get_NameTable()
0x56b54  stfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56b59  ldarg.0
0x56b5a  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56b5f  brtrue.s loc_56B75
0x56b61  ldarg.0
0x56b62  newobj   instance void System.Xml.NameTable::.ctor()
0x56b67  stfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56b6c  ldarg.0
0x56b6d  ldc.i4.0
0x56b6e  stfld    bool System.Xml.XmlSqlBinaryReader::xntFromSettings
0x56b73  br.s     loc_56B7C
0x56b75  ldarg.0
0x56b76  ldc.i4.1
0x56b77  stfld    bool System.Xml.XmlSqlBinaryReader::xntFromSettings
0x56b7c  ldarg.0
0x56b7d  ldarg.0
0x56b7e  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56b83  ldstr    aXml// "xml"
0x56b88  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x56b8d  stfld    string System.Xml.XmlSqlBinaryReader::xml
0x56b92  ldarg.0
0x56b93  ldarg.0
0x56b94  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56b99  ldstr    aXmlns// "xmlns"
0x56b9e  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x56ba3  stfld    string System.Xml.XmlSqlBinaryReader::xmlns
0x56ba8  ldarg.0
0x56ba9  ldarg.0
0x56baa  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56baf  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x56bb4  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x56bb9  stfld    string System.Xml.XmlSqlBinaryReader::nsxmlns
0x56bbe  ldarg.0
0x56bbf  ldarg.s  4
0x56bc1  stfld    string System.Xml.XmlSqlBinaryReader::baseUri
0x56bc6  ldarg.0
0x56bc7  ldc.i4.5
0x56bc8  stfld    valuetype ScanState System.Xml.XmlSqlBinaryReader::state
0x56bcd  ldarg.0
0x56bce  ldc.i4.0
0x56bcf  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlSqlBinaryReader::nodetype
0x56bd4  ldarg.0
0x56bd5  ldc.i4.0
0x56bd6  stfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x56bdb  ldarg.0
0x56bdc  ldc.i4.s 0x10
0x56bde  newarr   ElemInfo
0x56be3  stfld    valuetype ElemInfo[] System.Xml.XmlSqlBinaryReader::elementStack
0x56be8  ldarg.0
0x56be9  ldc.i4.8
0x56bea  newarr   AttrInfo
0x56bef  stfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x56bf4  ldarg.0
0x56bf5  ldc.i4.8
0x56bf6  newarr   [mscorlib]System.Int32
0x56bfb  stfld    int32[] System.Xml.XmlSqlBinaryReader::attrHashTbl
0x56c00  ldarg.0
0x56c01  ldflda   valuetype SymbolTables System.Xml.XmlSqlBinaryReader::symbolTables
0x56c06  call     instance void SymbolTables::Init()
0x56c0b  ldarg.0
0x56c0c  ldflda   valuetype QName System.Xml.XmlSqlBinaryReader::qnameOther
0x56c11  call     instance void QName::Clear()
0x56c16  ldarg.0
0x56c17  ldflda   valuetype QName System.Xml.XmlSqlBinaryReader::qnameElement
0x56c1c  call     instance void QName::Clear()
0x56c21  ldarg.0
0x56c22  ldc.i4.0
0x56c23  stfld    bool System.Xml.XmlSqlBinaryReader::xmlspacePreserve
0x56c28  ldarg.0
0x56c29  newobj   instance void System.Xml.SecureStringHasher::.ctor()
0x56c2e  stfld    class System.Xml.SecureStringHasher System.Xml.XmlSqlBinaryReader::hasher
0x56c33  ldarg.0
0x56c34  ldarg.0
0x56c35  ldfld    class System.Xml.SecureStringHasher System.Xml.XmlSqlBinaryReader::hasher
0x56c3a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class NamespaceDecl>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x56c3f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class NamespaceDecl> System.Xml.XmlSqlBinaryReader::namespaces
0x56c44  ldarg.0
0x56c45  ldsfld   string [mscorlib]System.String::Empty
0x56c4a  ldsfld   string [mscorlib]System.String::Empty
0x56c4f  call     instance void System.Xml.XmlSqlBinaryReader::AddInitNamespace(string prefix, string uri)
0x56c54  ldarg.0
0x56c55  ldarg.0
0x56c56  ldfld    string System.Xml.XmlSqlBinaryReader::xml
0x56c5b  ldarg.0
0x56c5c  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x56c61  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x56c66  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x56c6b  call     instance void System.Xml.XmlSqlBinaryReader::AddInitNamespace(string prefix, string uri)
0x56c70  ldarg.0
0x56c71  ldarg.0
0x56c72  ldfld    string System.Xml.XmlSqlBinaryReader::xmlns
0x56c77  ldarg.0
0x56c78  ldfld    string System.Xml.XmlSqlBinaryReader::nsxmlns
0x56c7d  call     instance void System.Xml.XmlSqlBinaryReader::AddInitNamespace(string prefix, string uri)
0x56c82  ldarg.0
0x56c83  ldsfld   class [mscorlib]System.Type System.Xml.XmlSqlBinaryReader::TypeOfString
0x56c88  stfld    class [mscorlib]System.Type System.Xml.XmlSqlBinaryReader::valueType
0x56c8d  ldarg.0
0x56c8e  ldarg.1
0x56c8f  stfld    class [mscorlib]System.IO.Stream System.Xml.XmlSqlBinaryReader::inStrm
0x56c94  ldarg.2
0x56c95  brfalse.s loc_56CB5
0x56c97  ldarg.0
0x56c98  ldarg.2
0x56c99  stfld    unsigned int8[] System.Xml.XmlSqlBinaryReader::data
0x56c9e  ldarg.0
0x56c9f  ldarg.3
0x56ca0  stfld    int32 System.Xml.XmlSqlBinaryReader::end
0x56ca5  ldarg.0
0x56ca6  ldc.i4.2
0x56ca7  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x56cac  ldarg.0
0x56cad  ldc.i4.1
0x56cae  stfld    bool System.Xml.XmlSqlBinaryReader::sniffed
0x56cb3  br.s     loc_56CEB
0x56cb5  ldarg.0
0x56cb6  ldc.i4   0x1000
0x56cbb  newarr   [mscorlib]System.Byte
0x56cc0  stfld    unsigned int8[] System.Xml.XmlSqlBinaryReader::data
0x56cc5  ldarg.0
0x56cc6  ldarg.1
0x56cc7  ldarg.0
0x56cc8  ldfld    unsigned int8[] System.Xml.XmlSqlBinaryReader::data
0x56ccd  ldc.i4.0
0x56cce  ldc.i4   0x1000
0x56cd3  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x56cd8  stfld    int32 System.Xml.XmlSqlBinaryReader::end
0x56cdd  ldarg.0
0x56cde  ldc.i4.0
0x56cdf  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x56ce4  ldarg.0
0x56ce5  ldc.i4.0
0x56ce6  stfld    bool System.Xml.XmlSqlBinaryReader::sniffed
0x56ceb  ldarg.0
0x56cec  ldc.i4.m1
0x56ced  stfld    int32 System.Xml.XmlSqlBinaryReader::mark
0x56cf2  ldarg.0
0x56cf3  ldarg.0
0x56cf4  ldfld    int32 System.Xml.XmlSqlBinaryReader::end
0x56cf9  ldc.i4.0
0x56cfa  ceq
0x56cfc  stfld    bool System.Xml.XmlSqlBinaryReader::eof
0x56d01  ldarg.0
0x56d02  ldc.i4.0
0x56d03  conv.i8
0x56d04  stfld    int64 System.Xml.XmlSqlBinaryReader::offset
0x56d09  ldarg.0
0x56d0a  ldarg.s  5
0x56d0c  stfld    bool System.Xml.XmlSqlBinaryReader::closeInput
0x56d11  ldarg.s  6
0x56d13  callvirt instance valuetype System.Xml.ConformanceLevel System.Xml.XmlReaderSettings::get_ConformanceLevel()
0x56d18  stloc.0
0x56d19  ldloc.0
0x56d1a  switch   loc_56D2D, loc_56D36, loc_56D40
0x56d2b  br.s     loc_56D47
0x56d2d  ldarg.0
0x56d2e  ldc.i4.0
0x56d2f  stfld    int32 System.Xml.XmlSqlBinaryReader::docState
0x56d34  br.s     loc_56D47
0x56d36  ldarg.0
0x56d37  ldc.i4.s 9
0x56d39  stfld    int32 System.Xml.XmlSqlBinaryReader::docState
0x56d3e  br.s     loc_56D47
0x56d40  ldarg.0
0x56d41  ldc.i4.1
0x56d42  stfld    int32 System.Xml.XmlSqlBinaryReader::docState
0x56d47  ldarg.0
0x56d48  ldarg.s  6
0x56d4a  callvirt instance bool System.Xml.XmlReaderSettings::get_CheckCharacters()
0x56d4f  stfld    bool System.Xml.XmlSqlBinaryReader::checkCharacters
0x56d54  ldarg.0
0x56d55  ldarg.s  6
0x56d57  callvirt instance valuetype System.Xml.DtdProcessing System.Xml.XmlReaderSettings::get_DtdProcessing()
0x56d5c  stfld    valuetype System.Xml.DtdProcessing System.Xml.XmlSqlBinaryReader::dtdProcessing
0x56d61  ldarg.0
0x56d62  ldarg.s  6
0x56d64  callvirt instance bool System.Xml.XmlReaderSettings::get_IgnoreWhitespace()
0x56d69  stfld    bool System.Xml.XmlSqlBinaryReader::ignoreWhitespace
0x56d6e  ldarg.0
0x56d6f  ldarg.s  6
0x56d71  callvirt instance bool System.Xml.XmlReaderSettings::get_IgnoreProcessingInstructions()
0x56d76  stfld    bool System.Xml.XmlSqlBinaryReader::ignorePIs
0x56d7b  ldarg.0
0x56d7c  ldarg.s  6
0x56d7e  callvirt instance bool System.Xml.XmlReaderSettings::get_IgnoreComments()
0x56d83  stfld    bool System.Xml.XmlSqlBinaryReader::ignoreComments
0x56d88  volatile.
0x56d8a  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Type[] System.Xml.XmlSqlBinaryReader::TokenTypeMap
0x56d8f  brtrue.s loc_56D97
0x56d91  ldarg.0
0x56d92  call     instance void System.Xml.XmlSqlBinaryReader::GenerateTokenTypeMap()
0x56d97  ret
```
