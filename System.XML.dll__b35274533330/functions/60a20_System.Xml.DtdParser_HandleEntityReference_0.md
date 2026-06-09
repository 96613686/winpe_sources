# System.Xml.DtdParser::HandleEntityReference_0

- ea: `0x60a20`
- end: `0x60b1e`
- name: `System.Xml.DtdParser::HandleEntityReference_0`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x60a00`

## callees

- `0x13320`
- `0x15e50`
- `0x5c5e0`
- `0x5c620`
- `0x60960`
- `0x609a0`
- `0x60a20`
- `0x60ba0`
- `0x60de0`
- `0x60df0`
- `0xc9980`
- `0xc99e0`
- `0xc9a70`

## string_xrefs

- `0x60a89`: `Xml_RecursiveGenEntity`
- `0x60a90`: `Xml_RecursiveParEntity`
- `0x60a4e`: `Xml_InvalidParEntityRef`

## pseudocode

```c

```

## disassembly

```asm
0x60a20  ldarg.0
0x60a21  call     instance void System.Xml.DtdParser::SaveParsingBuffer()
0x60a26  ldarg.2
0x60a27  brfalse.s loc_60A58
0x60a29  ldarg.0
0x60a2a  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x60a2f  brfalse.s loc_60A58
0x60a31  ldarg.0
0x60a32  call     instance bool System.Xml.DtdParser::get_ParsingTopLevelMarkup()
0x60a37  brtrue.s loc_60A58
0x60a39  ldarg.0
0x60a3a  ldarg.0
0x60a3b  ldfld    int32 System.Xml.DtdParser::curPos
0x60a40  ldarg.1
0x60a41  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60a46  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60a4b  sub
0x60a4c  ldc.i4.1
0x60a4d  sub
0x60a4e  ldstr    aXmlInvalidpare// "Xml_InvalidParEntityRef"
0x60a53  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x60a58  ldarg.0
0x60a59  ldarg.1
0x60a5a  ldarg.2
0x60a5b  ldc.i4.1
0x60a5c  ldarg.s  4
0x60a5e  call     instance class System.Xml.Schema.SchemaEntity System.Xml.DtdParser::VerifyEntityReference(class System.Xml.XmlQualifiedName entityName, bool paramEntity, bool mustBeDeclared, bool inAttribute)
0x60a63  stloc.0
0x60a64  ldloc.0
0x60a65  brtrue.s loc_60A69
0x60a67  ldc.i4.0
0x60a68  ret
0x60a69  ldloc.0
0x60a6a  callvirt instance bool System.Xml.Schema.SchemaEntity::get_ParsingInProgress()
0x60a6f  brfalse.s loc_60AA0
0x60a71  ldarg.0
0x60a72  ldarg.0
0x60a73  ldfld    int32 System.Xml.DtdParser::curPos
0x60a78  ldarg.1
0x60a79  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60a7e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60a83  sub
0x60a84  ldc.i4.1
0x60a85  sub
0x60a86  ldarg.2
0x60a87  brtrue.s loc_60A90
0x60a89  ldstr    aXmlRecursivege// "Xml_RecursiveGenEntity"
0x60a8e  br.s     loc_60A95
0x60a90  ldstr    aXmlRecursivepa// "Xml_RecursiveParEntity"
0x60a95  ldarg.1
0x60a96  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60a9b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x60aa0  ldloc.0
0x60aa1  callvirt instance bool System.Xml.Schema.SchemaEntity::get_IsExternal()
0x60aa6  brfalse.s loc_60ACA
0x60aa8  ldarg.0
0x60aa9  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x60aae  ldloc.0
0x60aaf  ldloca.s 1
0x60ab1  callvirt instance bool System.Xml.IDtdParserAdapter::PushEntity(class System.Xml.IDtdEntityInfo entity, [out] int32& entityId)
0x60ab6  brtrue.s loc_60ABA
0x60ab8  ldc.i4.0
0x60ab9  ret
0x60aba  ldarg.0
0x60abb  ldarg.0
0x60abc  ldfld    int32 System.Xml.DtdParser::externalEntitiesDepth
0x60ac1  ldc.i4.1
0x60ac2  add
0x60ac3  stfld    int32 System.Xml.DtdParser::externalEntitiesDepth
0x60ac8  br.s     loc_60AEB
0x60aca  ldloc.0
0x60acb  callvirt instance string System.Xml.Schema.SchemaEntity::get_Text()
0x60ad0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60ad5  brtrue.s loc_60AD9
0x60ad7  ldc.i4.0
0x60ad8  ret
0x60ad9  ldarg.0
0x60ada  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x60adf  ldloc.0
0x60ae0  ldloca.s 1
0x60ae2  callvirt instance bool System.Xml.IDtdParserAdapter::PushEntity(class System.Xml.IDtdEntityInfo entity, [out] int32& entityId)
0x60ae7  brtrue.s loc_60AEB
0x60ae9  ldc.i4.0
0x60aea  ret
0x60aeb  ldarg.0
0x60aec  ldloc.1
0x60aed  stfld    int32 System.Xml.DtdParser::currentEntityId
0x60af2  ldarg.2
0x60af3  brfalse.s loc_60B16
0x60af5  ldarg.3
0x60af6  brtrue.s loc_60B16
0x60af8  ldarg.0
0x60af9  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x60afe  ldc.i4.s 0x20
0x60b00  beq.s    loc_60B16
0x60b02  ldarg.0
0x60b03  ldarg.0
0x60b04  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x60b09  stfld    valuetype ScanningFunction System.Xml.DtdParser::savedScanningFunction
0x60b0e  ldarg.0
0x60b0f  ldc.i4.s 0x20
0x60b11  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x60b16  ldarg.0
0x60b17  call     instance void System.Xml.DtdParser::LoadParsingBuffer()
0x60b1c  ldc.i4.1
0x60b1d  ret
```
