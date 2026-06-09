# System.Xml.XmlTextReaderImpl::HandleEntityEnd

- ea: `0x2e0b0`
- end: `0x2e17c`
- name: `System.Xml.XmlTextReaderImpl::HandleEntityEnd`
- size: `204`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x28ed0`
- `0x28f80`
- `0x29980`
- `0x2b400`
- `0x2b7b0`
- `0x2cb40`
- `0x2d4b0`
- `0x30ff0`
- `0x102de0`
- `0x103020`
- `0x104440`
- `0x105de0`

## callees

- `0x29740`
- `0x2e0b0`
- `0x30510`

## string_xrefs

- `0x2e0ba`: `Xml_InternalError`
- `0x2e102`: `Xml_IncompleteEntity`
- `0x2e148`: `Xml_IncompleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2e0b0  ldarg.0
0x2e0b1  ldfld    int32 System.Xml.XmlTextReaderImpl::parsingStatesStackTop
0x2e0b6  ldc.i4.m1
0x2e0b7  bne.un.s loc_2E0C4
0x2e0b9  ldarg.0
0x2e0ba  ldstr    aXmlInternalerr// "Xml_InternalError"
0x2e0bf  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2e0c4  ldarg.0
0x2e0c5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e0ca  ldfld    bool ParsingState::entityResolvedManually
0x2e0cf  brfalse.s loc_2E125
0x2e0d1  ldarg.0
0x2e0d2  ldarg.0
0x2e0d3  ldfld    int32 System.Xml.XmlTextReaderImpl::index
0x2e0d8  ldc.i4.1
0x2e0d9  sub
0x2e0da  stfld    int32 System.Xml.XmlTextReaderImpl::index
0x2e0df  ldarg.1
0x2e0e0  brfalse.s loc_2E10C
0x2e0e2  ldarg.0
0x2e0e3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e0e8  ldfld    int32 ParsingState::entityId
0x2e0ed  ldarg.0
0x2e0ee  ldfld    class NodeData[] System.Xml.XmlTextReaderImpl::nodes
0x2e0f3  ldarg.0
0x2e0f4  ldfld    int32 System.Xml.XmlTextReaderImpl::index
0x2e0f9  ldelem.ref
0x2e0fa  ldfld    int32 NodeData::entityId
0x2e0ff  beq.s    loc_2E10C
0x2e101  ldarg.0
0x2e102  ldstr    aXmlIncompletee// "Xml_IncompleteEntity"
0x2e107  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2e10c  ldarg.0
0x2e10d  ldarg.0
0x2e10e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e113  ldfld    class System.Xml.IDtdEntityInfo ParsingState::entity
0x2e118  stfld    class System.Xml.IDtdEntityInfo System.Xml.XmlTextReaderImpl::lastEntity
0x2e11d  ldarg.0
0x2e11e  call     instance void System.Xml.XmlTextReaderImpl::PopEntity()
0x2e123  ldc.i4.1
0x2e124  ret
0x2e125  ldarg.1
0x2e126  brfalse.s loc_2E152
0x2e128  ldarg.0
0x2e129  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e12e  ldfld    int32 ParsingState::entityId
0x2e133  ldarg.0
0x2e134  ldfld    class NodeData[] System.Xml.XmlTextReaderImpl::nodes
0x2e139  ldarg.0
0x2e13a  ldfld    int32 System.Xml.XmlTextReaderImpl::index
0x2e13f  ldelem.ref
0x2e140  ldfld    int32 NodeData::entityId
0x2e145  beq.s    loc_2E152
0x2e147  ldarg.0
0x2e148  ldstr    aXmlIncompletee// "Xml_IncompleteEntity"
0x2e14d  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2e152  ldarg.0
0x2e153  call     instance void System.Xml.XmlTextReaderImpl::PopEntity()
0x2e158  ldarg.0
0x2e159  ldarg.0
0x2e15a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e15f  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2e164  stfld    class [mscorlib]System.Text.Encoding System.Xml.XmlTextReaderImpl::reportedEncoding
0x2e169  ldarg.0
0x2e16a  ldarg.0
0x2e16b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2e170  ldfld    string ParsingState::baseUriStr
0x2e175  stfld    string System.Xml.XmlTextReaderImpl::reportedBaseUri
0x2e17a  ldc.i4.0
0x2e17b  ret
```
