# MS.Internal.IO.Packaging.XmlSignatureManifest::ParseReference

- ea: `0x24ec0`
- end: `0x24fa4`
- name: `MS.Internal.IO.Packaging.XmlSignatureManifest::ParseReference`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x24c70`

## callees

- `0x22c40`
- `0x24d80`
- `0x24df0`
- `0x24e60`
- `0x24ec0`
- `0x24fb0`
- `0x25f90`
- `0x2c100`

## string_xrefs

- `0x24ee3`: `http://www.w3.org/2000/09/xmldsig#`

## pseudocode

```c

```

## disassembly

```asm
0x24ec0  ldnull
0x24ec1  stloc.0
0x24ec2  ldarg.0
0x24ec3  ldloca.s 0
0x24ec5  call     class [System]System.Uri MS.Internal.IO.Packaging.XmlSignatureManifest::ParsePartUri(class [System.Xml]System.Xml.XmlReader reader, [out] class MS.Internal.ContentType& contentType)
0x24eca  stloc.1
0x24ecb  ldnull
0x24ecc  stloc.2
0x24ecd  ldnull
0x24ece  stloc.3
0x24ecf  ldnull
0x24ed0  stloc.s  4
0x24ed2  ldnull
0x24ed3  stloc.s  5
0x24ed5  ldc.i4.0
0x24ed6  stloc.s  6
0x24ed8  br       loc_24F82
0x24edd  ldarg.0
0x24ede  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x24ee3  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x24ee8  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24eed  brtrue.s loc_24EF8
0x24eef  ldarg.0
0x24ef0  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x24ef5  ldc.i4.3
0x24ef6  beq.s    loc_24F08
0x24ef8  ldstr    aPackagesignatu// "PackageSignatureCorruption"
0x24efd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x24f02  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x24f07  throw
0x24f08  ldloc.3
0x24f09  brtrue.s loc_24F28
0x24f0b  ldarg.0
0x24f0c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x24f11  ldc.i4.s 0x16
0x24f13  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x24f18  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24f1d  brtrue.s loc_24F28
0x24f1f  ldarg.0
0x24f20  call     string MS.Internal.IO.Packaging.XmlSignatureManifest::ParseDigestAlgorithmTag(class [System.Xml]System.Xml.XmlReader reader)
0x24f25  stloc.3
0x24f26  br.s     loc_24F82
0x24f28  ldloc.s  4
0x24f2a  brtrue.s loc_24F4A
0x24f2c  ldarg.0
0x24f2d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x24f32  ldc.i4.s 0x17
0x24f34  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x24f39  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24f3e  brtrue.s loc_24F4A
0x24f40  ldarg.0
0x24f41  call     string MS.Internal.IO.Packaging.XmlSignatureManifest::ParseDigestValueTag(class [System.Xml]System.Xml.XmlReader reader)
0x24f46  stloc.s  4
0x24f48  br.s     loc_24F82
0x24f4a  ldloc.s  6
0x24f4c  brtrue.s loc_24F72
0x24f4e  ldarg.0
0x24f4f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x24f54  ldc.i4.s 0xE
0x24f56  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x24f5b  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24f60  brtrue.s loc_24F72
0x24f62  ldarg.0
0x24f63  ldloc.1
0x24f64  ldloca.s 2
0x24f66  call     class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.IO.Packaging.XmlSignatureManifest::ParseTransformsTag(class [System.Xml]System.Xml.XmlReader reader, class [System]System.Uri partUri, class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageRelationshipSelector>& relationshipSelectors)
0x24f6b  stloc.s  5
0x24f6d  ldc.i4.1
0x24f6e  stloc.s  6
0x24f70  br.s     loc_24F82
0x24f72  ldstr    aPackagesignatu// "PackageSignatureCorruption"
0x24f77  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x24f7c  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x24f81  throw
0x24f82  ldarg.0
0x24f83  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x24f88  brfalse.s loc_24F96
0x24f8a  ldarg.0
0x24f8b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x24f90  ldc.i4.1
0x24f91  beq      loc_24EDD
0x24f96  ldloc.1
0x24f97  ldloc.0
0x24f98  ldloc.3
0x24f99  ldloc.s  4
0x24f9b  ldloc.s  5
0x24f9d  ldloc.2
0x24f9e  newobj   instance void MS.Internal.IO.Packaging.PartManifestEntry::.ctor(class [System]System.Uri uri, class MS.Internal.ContentType contentType, string hashAlgorithm, string hashValue, class [mscorlib]System.Collections.Generic.List`1<string> transforms, class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageRelationshipSelector> relationshipSelectors)
0x24fa3  ret
```
