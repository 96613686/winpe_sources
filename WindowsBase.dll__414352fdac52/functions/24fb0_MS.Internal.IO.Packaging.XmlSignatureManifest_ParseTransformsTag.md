# MS.Internal.IO.Packaging.XmlSignatureManifest::ParseTransformsTag

- ea: `0x24fb0`
- end: `0x25107`
- name: `MS.Internal.IO.Packaging.XmlSignatureManifest::ParseTransformsTag`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x24ec0`

## callees

- `0x1f530`
- `0x24180`
- `0x24fb0`
- `0x25110`
- `0x25f90`
- `0x2c100`

## string_xrefs

- `0x24fe4`: `http://www.w3.org/2000/09/xmldsig#`
- `0x24fb8`: `XmlSignatureParseError`
- `0x25004`: `XmlSignatureParseError`
- `0x250ad`: `XmlSignatureParseError`
- `0x250d9`: `XmlSignatureParseError`

## pseudocode

```c

```

## disassembly

```asm
0x24fb0  ldarg.0
0x24fb1  call     int32 MS.Internal.IO.Packaging.PackagingUtilities::GetNonXmlnsAttributeCount(class [System.Xml]System.Xml.XmlReader reader)
0x24fb6  brfalse.s loc_24FC8
0x24fb8  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x24fbd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x24fc2  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x24fc7  throw
0x24fc8  ldnull
0x24fc9  stloc.0
0x24fca  ldc.i4.0
0x24fcb  stloc.1
0x24fcc  ldc.i4.0
0x24fcd  stloc.2
0x24fce  br       loc_250BD
0x24fd3  ldnull
0x24fd4  stloc.3
0x24fd5  ldarg.0
0x24fd6  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x24fdb  ldc.i4.4
0x24fdc  bne.un.s loc_25004
0x24fde  ldarg.0
0x24fdf  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x24fe4  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x24fe9  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x24fee  brtrue.s loc_25004
0x24ff0  ldarg.0
0x24ff1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x24ff6  ldc.i4.s 0xD
0x24ff8  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x24ffd  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x25002  brfalse.s loc_25014
0x25004  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x25009  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2500e  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x25013  throw
0x25014  ldarg.0
0x25015  call     int32 MS.Internal.IO.Packaging.PackagingUtilities::GetNonXmlnsAttributeCount(class [System.Xml]System.Xml.XmlReader reader)
0x2501a  ldc.i4.1
0x2501b  bne.un.s loc_2502B
0x2501d  ldarg.0
0x2501e  ldc.i4.s 0xF
0x25020  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x25025  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x2502a  stloc.3
0x2502b  ldloc.3
0x2502c  brfalse.s loc_250AD
0x2502e  ldloc.3
0x2502f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x25034  ldc.i4.0
0x25035  ble.s    loc_250AD
0x25037  ldloc.3
0x25038  ldc.i4.4
0x25039  call     string MS.Internal.IO.Packaging.XTable::Get(valuetype ID i)
0x2503e  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x25043  brtrue.s loc_2507B
0x25045  ldloc.1
0x25046  brtrue.s loc_2506B
0x25048  ldarg.0
0x25049  ldarg.1
0x2504a  ldarg.2
0x2504b  call     void MS.Internal.IO.Packaging.XmlSignatureManifest::ParseRelationshipsTransform(class [System.Xml]System.Xml.XmlReader reader, class [System]System.Uri partUri, class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageRelationshipSelector>& relationshipSelectors)
0x25050  ldloc.0
0x25051  brtrue.s loc_25059
0x25053  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x25058  stloc.0
0x25059  ldloc.0
0x2505a  ldloc.3
0x2505b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x25060  ldc.i4.1
0x25061  stloc.1
0x25062  ldloc.0
0x25063  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x25068  stloc.2
0x25069  br.s     loc_250BD
0x2506b  ldstr    aMultiplerelati// "MultipleRelationshipTransformsFound"
0x25070  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x25075  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x2507a  throw
0x2507b  ldarg.0
0x2507c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x25081  brfalse.s loc_250AD
0x25083  ldloc.0
0x25084  brtrue.s loc_2508C
0x25086  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2508b  stloc.0
0x2508c  ldloc.3
0x2508d  call     bool MS.Internal.IO.Packaging.XmlDigitalSignatureProcessor::IsValidXmlCanonicalizationTransform(string transformName)
0x25092  brfalse.s loc_2509D
0x25094  ldloc.0
0x25095  ldloc.3
0x25096  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2509b  br.s     loc_250BD
0x2509d  ldstr    aUnsupportedtra// "UnsupportedTransformAlgorithm"
0x250a2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x250a7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x250ac  throw
0x250ad  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x250b2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x250b7  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x250bc  throw
0x250bd  ldarg.0
0x250be  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x250c3  brfalse.s loc_250D1
0x250c5  ldarg.0
0x250c6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x250cb  ldc.i4.1
0x250cc  beq      loc_24FD3
0x250d1  ldloc.0
0x250d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x250d7  brtrue.s loc_250E9
0x250d9  ldstr    aXmlsignaturepa// "XmlSignatureParseError"
0x250de  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x250e3  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x250e8  throw
0x250e9  ldloc.1
0x250ea  brfalse.s loc_25105
0x250ec  ldloc.0
0x250ed  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x250f2  ldloc.2
0x250f3  bne.un.s loc_25105
0x250f5  ldstr    aRelationshiptr// "RelationshipTransformNotFollowedByCanon"...
0x250fa  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x250ff  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x25104  throw
0x25105  ldloc.0
0x25106  ret
```
