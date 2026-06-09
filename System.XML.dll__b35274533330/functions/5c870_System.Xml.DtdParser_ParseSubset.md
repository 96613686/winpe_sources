# System.Xml.DtdParser::ParseSubset

- ea: `0x5c870`
- end: `0x5caa5`
- name: `System.Xml.DtdParser::ParseSubset`
- size: `565`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5c800`
- `0x5c810`
- `0x5c870`

## callees

- `0x5c5e0`
- `0x5c870`
- `0x5cab0`
- `0x5d0a0`
- `0x5d520`
- `0x5d700`
- `0x5d850`
- `0x5d8d0`
- `0x5d920`
- `0x5dc90`
- `0x609b0`
- `0x60cd0`
- `0x60de0`
- `0x60f10`
- `0xc9b80`

## string_xrefs

- `0x5c90c`: `Xml_InvalidConditionalSection`
- `0x5c987`: `Xml_UnexpectedCDataEnd`
- `0x5c9ad`: `Xml_UnclosedConditionalSection`
- `0x5ca49`: `Xml_UnclosedConditionalSection`
- `0x5ca0e`: `Xml_ExpectDtdMarkup`
- `0x5ca30`: `Xml_IncompleteDtdContent`

## pseudocode

```c

```

## disassembly

```asm
0x5c870  ldarg.0
0x5c871  ldc.i4.0
0x5c872  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5c877  stloc.1
0x5c878  ldarg.0
0x5c879  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5c87e  stloc.0
0x5c87f  ldloc.1
0x5c880  ldc.i4.s 0xB
0x5c882  sub
0x5c883  switch   loc_5C8B9, loc_5C8C4, loc_5C8CF, loc_5C8DA, loc_5C8E5, loc_5C8F0, loc_5C8FB, loc_5C928, loc_5CA19
0x5c8ac  ldloc.1
0x5c8ad  ldc.i4.s 0x20
0x5c8af  beq      loc_5C996
0x5c8b4  br       loc_5CA54
0x5c8b9  ldarg.0
0x5c8ba  call     instance void System.Xml.DtdParser::ParseAttlistDecl()
0x5c8bf  br       loc_5CA54
0x5c8c4  ldarg.0
0x5c8c5  call     instance void System.Xml.DtdParser::ParseElementDecl()
0x5c8ca  br       loc_5CA54
0x5c8cf  ldarg.0
0x5c8d0  call     instance void System.Xml.DtdParser::ParseEntityDecl()
0x5c8d5  br       loc_5CA54
0x5c8da  ldarg.0
0x5c8db  call     instance void System.Xml.DtdParser::ParseNotationDecl()
0x5c8e0  br       loc_5CA54
0x5c8e5  ldarg.0
0x5c8e6  call     instance void System.Xml.DtdParser::ParseComment()
0x5c8eb  br       loc_5CA54
0x5c8f0  ldarg.0
0x5c8f1  call     instance void System.Xml.DtdParser::ParsePI()
0x5c8f6  br       loc_5CA54
0x5c8fb  ldarg.0
0x5c8fc  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x5c901  brfalse.s loc_5C916
0x5c903  ldarg.0
0x5c904  ldarg.0
0x5c905  ldfld    int32 System.Xml.DtdParser::curPos
0x5c90a  ldc.i4.3
0x5c90b  sub
0x5c90c  ldstr    aXmlInvalidcond// "Xml_InvalidConditionalSection"
0x5c911  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5c916  ldarg.0
0x5c917  call     instance void System.Xml.DtdParser::ParseCondSection()
0x5c91c  ldarg.0
0x5c91d  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5c922  stloc.0
0x5c923  br       loc_5CA54
0x5c928  ldarg.0
0x5c929  ldfld    int32 System.Xml.DtdParser::condSectionDepth
0x5c92e  ldc.i4.0
0x5c92f  ble.s    loc_5C97E
0x5c931  ldarg.0
0x5c932  ldarg.0
0x5c933  ldfld    int32 System.Xml.DtdParser::condSectionDepth
0x5c938  ldc.i4.1
0x5c939  sub
0x5c93a  stfld    int32 System.Xml.DtdParser::condSectionDepth
0x5c93f  ldarg.0
0x5c940  ldfld    bool System.Xml.DtdParser::validate
0x5c945  brfalse  loc_5CA54
0x5c94a  ldarg.0
0x5c94b  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5c950  ldarg.0
0x5c951  ldfld    int32[] System.Xml.DtdParser::condSectionEntityIds
0x5c956  ldarg.0
0x5c957  ldfld    int32 System.Xml.DtdParser::condSectionDepth
0x5c95c  ldelem.i4
0x5c95d  beq      loc_5CA54
0x5c962  ldarg.0
0x5c963  ldarg.0
0x5c964  ldfld    int32 System.Xml.DtdParser::curPos
0x5c969  ldc.i4.0
0x5c96a  ldstr    aSchParentityre// "Sch_ParEntityRefNesting"
0x5c96f  ldsfld   string [mscorlib]System.String::Empty
0x5c974  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x5c979  br       loc_5CA54
0x5c97e  ldarg.0
0x5c97f  ldarg.0
0x5c980  ldfld    int32 System.Xml.DtdParser::curPos
0x5c985  ldc.i4.3
0x5c986  sub
0x5c987  ldstr    aXmlUnexpectedc// "Xml_UnexpectedCDataEnd"
0x5c98c  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5c991  br       loc_5CA54
0x5c996  ldarg.0
0x5c997  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x5c99c  brfalse.s loc_5CA07
0x5c99e  ldarg.0
0x5c99f  ldfld    int32 System.Xml.DtdParser::condSectionDepth
0x5c9a4  brfalse.s loc_5C9B7
0x5c9a6  ldarg.0
0x5c9a7  ldarg.0
0x5c9a8  ldfld    int32 System.Xml.DtdParser::curPos
0x5c9ad  ldstr    aXmlUnclosedcon// "Xml_UnclosedConditionalSection"
0x5c9b2  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5c9b7  ldarg.0
0x5c9b8  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.DtdParser::internalSubsetValueSb
0x5c9bd  brfalse.s loc_5C9EA
0x5c9bf  ldarg.0
0x5c9c0  ldarg.0
0x5c9c1  ldfld    int32 System.Xml.DtdParser::curPos
0x5c9c6  ldc.i4.1
0x5c9c7  sub
0x5c9c8  call     instance void System.Xml.DtdParser::SaveParsingBuffer(int32 internalSubsetValueEndPos)
0x5c9cd  ldarg.0
0x5c9ce  ldfld    class System.Xml.Schema.SchemaInfo System.Xml.DtdParser::schemaInfo
0x5c9d3  ldarg.0
0x5c9d4  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.DtdParser::internalSubsetValueSb
0x5c9d9  callvirt instance string [mscorlib]System.Object::ToString()
0x5c9de  callvirt instance void System.Xml.Schema.SchemaInfo::set_InternalDtdSubset(string value)
0x5c9e3  ldarg.0
0x5c9e4  ldnull
0x5c9e5  stfld    class [mscorlib]System.Text.StringBuilder System.Xml.DtdParser::internalSubsetValueSb
0x5c9ea  ldarg.0
0x5c9eb  ldc.i4.0
0x5c9ec  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5c9f1  ldc.i4.s 0x1D
0x5c9f3  beq.s    loc_5CA18
0x5c9f5  ldarg.0
0x5c9f6  ldarg.0
0x5c9f7  ldfld    int32 System.Xml.DtdParser::curPos
0x5c9fc  ldstr    asc_12A30E// ">"
0x5ca01  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x5ca06  ret
0x5ca07  ldarg.0
0x5ca08  ldarg.0
0x5ca09  ldfld    int32 System.Xml.DtdParser::curPos
0x5ca0e  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x5ca13  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ca18  ret
0x5ca19  ldarg.0
0x5ca1a  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x5ca1f  brfalse.s loc_5CA3A
0x5ca21  ldarg.0
0x5ca22  ldfld    bool System.Xml.DtdParser::freeFloatingDtd
0x5ca27  brtrue.s loc_5CA3A
0x5ca29  ldarg.0
0x5ca2a  ldarg.0
0x5ca2b  ldfld    int32 System.Xml.DtdParser::curPos
0x5ca30  ldstr    aXmlIncompleted// "Xml_IncompleteDtdContent"
0x5ca35  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ca3a  ldarg.0
0x5ca3b  ldfld    int32 System.Xml.DtdParser::condSectionDepth
0x5ca40  brfalse.s loc_5CA53
0x5ca42  ldarg.0
0x5ca43  ldarg.0
0x5ca44  ldfld    int32 System.Xml.DtdParser::curPos
0x5ca49  ldstr    aXmlUnclosedcon// "Xml_UnclosedConditionalSection"
0x5ca4e  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ca53  ret
0x5ca54  ldarg.0
0x5ca55  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5ca5a  ldloc.0
0x5ca5b  beq      System.Xml.DtdParser__ParseSubset
0x5ca60  ldarg.0
0x5ca61  ldfld    bool System.Xml.DtdParser::validate
0x5ca66  brfalse.s loc_5CA84
0x5ca68  ldarg.0
0x5ca69  ldarg.0
0x5ca6a  ldfld    int32 System.Xml.DtdParser::curPos
0x5ca6f  ldc.i4.0
0x5ca70  ldstr    aSchParentityre// "Sch_ParEntityRefNesting"
0x5ca75  ldsfld   string [mscorlib]System.String::Empty
0x5ca7a  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x5ca7f  br       System.Xml.DtdParser__ParseSubset
0x5ca84  ldarg.0
0x5ca85  ldfld    bool System.Xml.DtdParser::v1Compat
0x5ca8a  brtrue   System.Xml.DtdParser__ParseSubset
0x5ca8f  ldarg.0
0x5ca90  ldarg.0
0x5ca91  ldfld    int32 System.Xml.DtdParser::curPos
0x5ca96  ldstr    aSchParentityre// "Sch_ParEntityRefNesting"
0x5ca9b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5caa0  br       System.Xml.DtdParser__ParseSubset
```
