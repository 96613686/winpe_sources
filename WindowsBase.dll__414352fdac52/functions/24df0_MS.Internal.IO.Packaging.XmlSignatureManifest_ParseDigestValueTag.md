# MS.Internal.IO.Packaging.XmlSignatureManifest::ParseDigestValueTag

- ea: `0x24df0`
- end: `0x24e54`
- name: `MS.Internal.IO.Packaging.XmlSignatureManifest::ParseDigestValueTag`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x24ec0`

## callees

- `0x1f530`
- `0x24df0`
- `0x2c100`

## string_xrefs

- `0x24dff`: `http://www.w3.org/2000/09/xmldsig#`
- `0x24e14`: `XmlSignatureParseError`
- `0x24e3d`: `XmlSignatureParseError`

## pseudocode

```c

```

## disassembly

```asm
0x24df0  ldarg.0
0x24df1  call     int32 MS.Internal.IO.Packaging.PackagingUtilities::GetNonXmlnsAttributeCount(class [System.Xml]System.Xml.XmlReader reader)
0x24df6  ldc.i4.0
0x24df7  bgt.s    loc_24E14
0x24df9  ldarg.0
0x24dfa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x24dff  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x24e04  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24e09  brtrue.s loc_24E14
0x24e0b  ldarg.0
0x24e0c  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x24e11  ldc.i4.3
0x24e12  beq.s    loc_24E24
0x24e14  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x24e19  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x24e1e  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x24e23  throw
0x24e24  ldarg.0
0x24e25  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_HasAttributes()
0x24e2a  brtrue.s loc_24E3D
0x24e2c  ldarg.0
0x24e2d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x24e32  brfalse.s loc_24E4D
0x24e34  ldarg.0
0x24e35  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x24e3a  ldc.i4.3
0x24e3b  beq.s    loc_24E4D
0x24e3d  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x24e42  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x24e47  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x24e4c  throw
0x24e4d  ldarg.0
0x24e4e  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x24e53  ret
```
