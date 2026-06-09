# System.Xml.DtdParser::VerifyEntityReference

- ea: `0x60ba0`
- end: `0x60cd0`
- name: `System.Xml.DtdParser::VerifyEntityReference`
- size: `304`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x5f4d0`
- `0x60a20`
- `0x120050`
- `0x1223d0`

## callees

- `0x13320`
- `0x13380`
- `0x5c5e0`
- `0x60ba0`
- `0x60cd0`
- `0x60df0`
- `0xc9980`
- `0xc99c0`
- `0xc9bb0`
- `0xc9bd0`

## string_xrefs

- `0x60c32`: `Xml_UndeclaredEntity`
- `0x60c59`: `Xml_UndeclaredEntity`
- `0x60c8d`: `Xml_UnparsedEntityRef`
- `0x60cbe`: `Xml_ExternalEntityInAttValue`
- `0x60bf7`: `Xml_UndeclaredParEntity`

## pseudocode

```c

```

## disassembly

```asm
0x60ba0  ldarg.2
0x60ba1  brfalse.s loc_60BB9
0x60ba3  ldarg.0
0x60ba4  ldfld    class System.Xml.Schema.SchemaInfo System.Xml.DtdParser::schemaInfo
0x60ba9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.XmlQualifiedName, class System.Xml.Schema.SchemaEntity> System.Xml.Schema.SchemaInfo::get_ParameterEntities()
0x60bae  ldarg.1
0x60baf  ldloca.s 0
0x60bb1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.XmlQualifiedName, class System.Xml.Schema.SchemaEntity>::TryGetValue(var<u1>, !!T0)
0x60bb6  pop
0x60bb7  br.s     loc_60BCD
0x60bb9  ldarg.0
0x60bba  ldfld    class System.Xml.Schema.SchemaInfo System.Xml.DtdParser::schemaInfo
0x60bbf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.XmlQualifiedName, class System.Xml.Schema.SchemaEntity> System.Xml.Schema.SchemaInfo::get_GeneralEntities()
0x60bc4  ldarg.1
0x60bc5  ldloca.s 0
0x60bc7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.XmlQualifiedName, class System.Xml.Schema.SchemaEntity>::TryGetValue(var<u1>, !!T0)
0x60bcc  pop
0x60bcd  ldloc.0
0x60bce  brtrue   loc_60C6B
0x60bd3  ldarg.2
0x60bd4  brfalse.s loc_60C09
0x60bd6  ldarg.0
0x60bd7  ldfld    bool System.Xml.DtdParser::validate
0x60bdc  brfalse  loc_60C69
0x60be1  ldarg.0
0x60be2  ldarg.0
0x60be3  ldfld    int32 System.Xml.DtdParser::curPos
0x60be8  ldarg.1
0x60be9  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60bee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60bf3  sub
0x60bf4  ldc.i4.1
0x60bf5  sub
0x60bf6  ldc.i4.0
0x60bf7  ldstr    aXmlUndeclaredp// "Xml_UndeclaredParEntity"
0x60bfc  ldarg.1
0x60bfd  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c02  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x60c07  br.s     loc_60C69
0x60c09  ldarg.3
0x60c0a  brfalse.s loc_60C69
0x60c0c  ldarg.0
0x60c0d  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x60c12  brtrue.s loc_60C44
0x60c14  ldarg.0
0x60c15  ldfld    bool System.Xml.DtdParser::validate
0x60c1a  brfalse.s loc_60C69
0x60c1c  ldarg.0
0x60c1d  ldarg.0
0x60c1e  ldfld    int32 System.Xml.DtdParser::curPos
0x60c23  ldarg.1
0x60c24  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c29  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60c2e  sub
0x60c2f  ldc.i4.1
0x60c30  sub
0x60c31  ldc.i4.0
0x60c32  ldstr    aXmlUndeclarede// "Xml_UndeclaredEntity"
0x60c37  ldarg.1
0x60c38  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c3d  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x60c42  br.s     loc_60C69
0x60c44  ldarg.0
0x60c45  ldarg.0
0x60c46  ldfld    int32 System.Xml.DtdParser::curPos
0x60c4b  ldarg.1
0x60c4c  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c51  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60c56  sub
0x60c57  ldc.i4.1
0x60c58  sub
0x60c59  ldstr    aXmlUndeclarede// "Xml_UndeclaredEntity"
0x60c5e  ldarg.1
0x60c5f  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c64  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x60c69  ldnull
0x60c6a  ret
0x60c6b  ldloc.0
0x60c6c  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.SchemaEntity::get_NData()
0x60c71  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x60c76  brtrue.s loc_60C9D
0x60c78  ldarg.0
0x60c79  ldarg.0
0x60c7a  ldfld    int32 System.Xml.DtdParser::curPos
0x60c7f  ldarg.1
0x60c80  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c85  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60c8a  sub
0x60c8b  ldc.i4.1
0x60c8c  sub
0x60c8d  ldstr    aXmlUnparsedent// "Xml_UnparsedEntityRef"
0x60c92  ldarg.1
0x60c93  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60c98  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x60c9d  ldarg.s  4
0x60c9f  brfalse.s loc_60CCE
0x60ca1  ldloc.0
0x60ca2  callvirt instance bool System.Xml.Schema.SchemaEntity::get_IsExternal()
0x60ca7  brfalse.s loc_60CCE
0x60ca9  ldarg.0
0x60caa  ldarg.0
0x60cab  ldfld    int32 System.Xml.DtdParser::curPos
0x60cb0  ldarg.1
0x60cb1  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60cb6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x60cbb  sub
0x60cbc  ldc.i4.1
0x60cbd  sub
0x60cbe  ldstr    aXmlExternalent_0// "Xml_ExternalEntityInAttValue"
0x60cc3  ldarg.1
0x60cc4  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x60cc9  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x60cce  ldloc.0
0x60ccf  ret
```
