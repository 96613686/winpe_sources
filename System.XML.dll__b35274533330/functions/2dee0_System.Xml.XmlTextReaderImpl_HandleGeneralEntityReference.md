# System.Xml.XmlTextReaderImpl::HandleGeneralEntityReference

- ea: `0x2dee0`
- end: `0x2e09b`
- name: `System.Xml.XmlTextReaderImpl::HandleGeneralEntityReference`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x284d0`
- `0x2dd60`

## callees

- `0x132d0`
- `0x15ab0`
- `0x15c10`
- `0x15c20`
- `0x15c30`
- `0x15c40`
- `0x20e90`
- `0x294b0`
- `0x297a0`
- `0x2dee0`
- `0x303c0`
- `0x30480`
- `0x31650`
- `0xc9800`
- `0xc99f0`
- `0xfe500`

## string_xrefs

- `0x2df4b`: `Xml_UndeclaredEntity`
- `0x2df90`: `Xml_UnparsedEntityRef`
- `0x2dfb9`: `Xml_ExternalEntityInStandAloneDocument`
- `0x2dfe5`: `Xml_ExternalEntityInAttValue`

## pseudocode

```c

```

## disassembly

```asm
0x2dee0  ldnull
0x2dee1  stloc.0
0x2dee2  ldarg.0
0x2dee3  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x2dee8  brtrue.s loc_2DF0E
0x2deea  ldarg.0
0x2deeb  ldfld    class System.Xml.XmlParserContext System.Xml.XmlTextReaderImpl::fragmentParserContext
0x2def0  brfalse.s loc_2DF0E
0x2def2  ldarg.0
0x2def3  ldfld    class System.Xml.XmlParserContext System.Xml.XmlTextReaderImpl::fragmentParserContext
0x2def8  callvirt instance bool System.Xml.XmlParserContext::get_HasDtdInfo()
0x2defd  brfalse.s loc_2DF0E
0x2deff  ldarg.0
0x2df00  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x2df05  ldc.i4.2
0x2df06  bne.un.s loc_2DF0E
0x2df08  ldarg.0
0x2df09  call     instance void System.Xml.XmlTextReaderImpl::ParseDtdFromParserContext()
0x2df0e  ldarg.0
0x2df0f  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x2df14  brfalse.s loc_2DF26
0x2df16  ldarg.0
0x2df17  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x2df1c  ldarg.1
0x2df1d  callvirt instance class System.Xml.IDtdEntityInfo System.Xml.IDtdInfo::LookupEntity(string name)
0x2df22  dup
0x2df23  stloc.0
0x2df24  brtrue.s loc_2DF63
0x2df26  ldarg.0
0x2df27  ldfld    bool System.Xml.XmlTextReaderImpl::disableUndeclaredEntityCheck
0x2df2c  brfalse.s loc_2DF4A
0x2df2e  ldarg.1
0x2df2f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0x2df34  ldc.i4.0
0x2df35  newobj   instance void System.Xml.Schema.SchemaEntity::.ctor(class System.Xml.XmlQualifiedName qname, bool isParameter)
0x2df3a  stloc.1
0x2df3b  ldloc.1
0x2df3c  ldsfld   string [mscorlib]System.String::Empty
0x2df41  callvirt instance void System.Xml.Schema.SchemaEntity::set_Text(string value)
0x2df46  ldloc.1
0x2df47  stloc.0
0x2df48  br.s     loc_2DF63
0x2df4a  ldarg.0
0x2df4b  ldstr    aXmlUndeclarede// "Xml_UndeclaredEntity"
0x2df50  ldarg.1
0x2df51  ldarg.0
0x2df52  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2df57  call     instance int32 ParsingState::get_LineNo()
0x2df5c  ldarg.s  4
0x2df5e  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x2df63  ldloc.0
0x2df64  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsUnparsedEntity()
0x2df69  brfalse.s loc_2DFA8
0x2df6b  ldarg.0
0x2df6c  ldfld    bool System.Xml.XmlTextReaderImpl::disableUndeclaredEntityCheck
0x2df71  brfalse.s loc_2DF8F
0x2df73  ldarg.1
0x2df74  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0x2df79  ldc.i4.0
0x2df7a  newobj   instance void System.Xml.Schema.SchemaEntity::.ctor(class System.Xml.XmlQualifiedName qname, bool isParameter)
0x2df7f  stloc.2
0x2df80  ldloc.2
0x2df81  ldsfld   string [mscorlib]System.String::Empty
0x2df86  callvirt instance void System.Xml.Schema.SchemaEntity::set_Text(string value)
0x2df8b  ldloc.2
0x2df8c  stloc.0
0x2df8d  br.s     loc_2DFA8
0x2df8f  ldarg.0
0x2df90  ldstr    aXmlUnparsedent// "Xml_UnparsedEntityRef"
0x2df95  ldarg.1
0x2df96  ldarg.0
0x2df97  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2df9c  call     instance int32 ParsingState::get_LineNo()
0x2dfa1  ldarg.s  4
0x2dfa3  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x2dfa8  ldarg.0
0x2dfa9  ldfld    bool System.Xml.XmlTextReaderImpl::standalone
0x2dfae  brfalse.s loc_2DFD6
0x2dfb0  ldloc.0
0x2dfb1  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsDeclaredInExternal()
0x2dfb6  brfalse.s loc_2DFD6
0x2dfb8  ldarg.0
0x2dfb9  ldstr    aXmlExternalent// "Xml_ExternalEntityInStandAloneDocument"
0x2dfbe  ldloc.0
0x2dfbf  callvirt instance string System.Xml.IDtdEntityInfo::get_Name()
0x2dfc4  ldarg.0
0x2dfc5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2dfca  call     instance int32 ParsingState::get_LineNo()
0x2dfcf  ldarg.s  4
0x2dfd1  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x2dfd6  ldloc.0
0x2dfd7  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsExternal()
0x2dfdc  brfalse  loc_2E064
0x2dfe1  ldarg.2
0x2dfe2  brfalse.s loc_2DFFF
0x2dfe4  ldarg.0
0x2dfe5  ldstr    aXmlExternalent_0// "Xml_ExternalEntityInAttValue"
0x2dfea  ldarg.1
0x2dfeb  ldarg.0
0x2dfec  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2dff1  call     instance int32 ParsingState::get_LineNo()
0x2dff6  ldarg.s  4
0x2dff8  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x2dffd  ldc.i4.4
0x2dffe  ret
0x2dfff  ldarg.0
0x2e000  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e005  ldc.i4.2
0x2e006  bne.un.s loc_2E00A
0x2e008  ldc.i4.4
0x2e009  ret
0x2e00a  ldarg.0
0x2e00b  call     instance bool System.Xml.XmlTextReaderImpl::get_IsResolverNull()
0x2e010  brfalse.s loc_2E037
0x2e012  ldarg.3
0x2e013  brfalse.s loc_2E035
0x2e015  ldarg.0
0x2e016  ldloc.0
0x2e017  call     instance bool System.Xml.XmlTextReaderImpl::PushExternalEntity(class System.Xml.IDtdEntityInfo entity)
0x2e01c  pop
0x2e01d  ldarg.0
0x2e01e  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e023  ldarg.0
0x2e024  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e029  ldfld    int32 ParsingState::entityId
0x2e02e  stfld    int32 NodeData::entityId
0x2e033  ldc.i4.5
0x2e034  ret
0x2e035  ldc.i4.4
0x2e036  ret
0x2e037  ldarg.0
0x2e038  ldloc.0
0x2e039  call     instance bool System.Xml.XmlTextReaderImpl::PushExternalEntity(class System.Xml.IDtdEntityInfo entity)
0x2e03e  pop
0x2e03f  ldarg.0
0x2e040  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e045  ldarg.0
0x2e046  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e04b  ldfld    int32 ParsingState::entityId
0x2e050  stfld    int32 NodeData::entityId
0x2e055  ldarg.2
0x2e056  brfalse.s loc_2E060
0x2e058  ldarg.0
0x2e059  ldfld    bool System.Xml.XmlTextReaderImpl::validatingReaderCompatFlag
0x2e05e  brtrue.s loc_2E062
0x2e060  ldc.i4.3
0x2e061  ret
0x2e062  ldc.i4.7
0x2e063  ret
0x2e064  ldarg.0
0x2e065  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2e06a  ldc.i4.2
0x2e06b  bne.un.s loc_2E06F
0x2e06d  ldc.i4.4
0x2e06e  ret
0x2e06f  ldarg.0
0x2e070  ldloc.0
0x2e071  call     instance void System.Xml.XmlTextReaderImpl::PushInternalEntity(class System.Xml.IDtdEntityInfo entity)
0x2e076  ldarg.0
0x2e077  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x2e07c  ldarg.0
0x2e07d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e082  ldfld    int32 ParsingState::entityId
0x2e087  stfld    int32 NodeData::entityId
0x2e08c  ldarg.2
0x2e08d  brfalse.s loc_2E097
0x2e08f  ldarg.0
0x2e090  ldfld    bool System.Xml.XmlTextReaderImpl::validatingReaderCompatFlag
0x2e095  brtrue.s loc_2E099
0x2e097  ldc.i4.3
0x2e098  ret
0x2e099  ldc.i4.7
0x2e09a  ret
```
