# System.Xml.XmlTextReaderImpl::ParseDocumentContent

- ea: `0x2b400`
- end: `0x2b7a8`
- name: `System.Xml.XmlTextReaderImpl::ParseDocumentContent`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x27ee0`

## callees

- `0x10e60`
- `0x29720`
- `0x29740`
- `0x29890`
- `0x2a510`
- `0x2b400`
- `0x2baa0`
- `0x2d230`
- `0x2dba0`
- `0x2dd10`
- `0x2dd60`
- `0x2e0a0`
- `0x2e0b0`
- `0x2e180`
- `0x2e260`
- `0x2e750`
- `0x2e780`
- `0x2eb20`
- `0x2ffb0`
- `0x31390`
- `0x313b0`
- `0x31420`

## string_xrefs

- `0x2b75e`: `Xml_MissingRoot`
- `0x2b545`: `Xml_InvalidRootData`
- `0x2b631`: `Xml_InvalidRootData`
- `0x2b725`: `Xml_InvalidRootData`
- `0x2b59b`: `Xml_BadDTDLocation`
- `0x2b5c4`: `Xml_UnexpectedEndTag`
- `0x2b5e7`: `Xml_MultipleRoots`

## pseudocode

```c

```

## disassembly

```asm
0x2b400  ldc.i4.0
0x2b401  stloc.0
0x2b402  ldc.i4.0
0x2b403  stloc.1
0x2b404  ldarg.0
0x2b405  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b40a  ldfld    int32 ParsingState::charPos
0x2b40f  stloc.2
0x2b410  ldarg.0
0x2b411  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b416  ldfld    char[] ParsingState::chars
0x2b41b  stloc.3
0x2b41c  ldloc.3
0x2b41d  ldloc.2
0x2b41e  ldelem.u2
0x2b41f  ldc.i4.s 0x3C
0x2b421  bne.un   loc_2B61B
0x2b426  ldc.i4.1
0x2b427  stloc.1
0x2b428  ldarg.0
0x2b429  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b42e  ldfld    int32 ParsingState::charsUsed
0x2b433  ldloc.2
0x2b434  sub
0x2b435  ldc.i4.4
0x2b436  blt      loc_2B70B
0x2b43b  ldloc.2
0x2b43c  ldc.i4.1
0x2b43d  add
0x2b43e  stloc.2
0x2b43f  ldloc.3
0x2b440  ldloc.2
0x2b441  ldelem.u2
0x2b442  stloc.s  4
0x2b444  ldloc.s  4
0x2b446  ldc.i4.s 0x21
0x2b448  beq.s    loc_2B474
0x2b44a  ldloc.s  4
0x2b44c  ldc.i4.s 0x2F
0x2b44e  beq      loc_2B5C0
0x2b453  ldloc.s  4
0x2b455  ldc.i4.s 0x3F
0x2b457  bne.un   loc_2B5D3
0x2b45c  ldarg.0
0x2b45d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b462  ldloc.2
0x2b463  ldc.i4.1
0x2b464  add
0x2b465  stfld    int32 ParsingState::charPos
0x2b46a  ldarg.0
0x2b46b  call     instance bool System.Xml.XmlTextReaderImpl::ParsePI()
0x2b470  brfalse.s loc_2B402
0x2b472  ldc.i4.1
0x2b473  ret
0x2b474  ldloc.2
0x2b475  ldc.i4.1
0x2b476  add
0x2b477  stloc.2
0x2b478  ldarg.0
0x2b479  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b47e  ldfld    int32 ParsingState::charsUsed
0x2b483  ldloc.2
0x2b484  sub
0x2b485  ldc.i4.2
0x2b486  blt      loc_2B70B
0x2b48b  ldloc.3
0x2b48c  ldloc.2
0x2b48d  ldelem.u2
0x2b48e  ldc.i4.s 0x2D
0x2b490  bne.un.s loc_2B4C9
0x2b492  ldloc.3
0x2b493  ldloc.2
0x2b494  ldc.i4.1
0x2b495  add
0x2b496  ldelem.u2
0x2b497  ldc.i4.s 0x2D
0x2b499  bne.un.s loc_2B4B6
0x2b49b  ldarg.0
0x2b49c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b4a1  ldloc.2
0x2b4a2  ldc.i4.2
0x2b4a3  add
0x2b4a4  stfld    int32 ParsingState::charPos
0x2b4a9  ldarg.0
0x2b4aa  call     instance bool System.Xml.XmlTextReaderImpl::ParseComment()
0x2b4af  brfalse  loc_2B402
0x2b4b4  ldc.i4.1
0x2b4b5  ret
0x2b4b6  ldarg.0
0x2b4b7  ldloc.2
0x2b4b8  ldc.i4.1
0x2b4b9  add
0x2b4ba  ldstr    asc_12B3DE// "-"
0x2b4bf  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x2b4c4  br       loc_2B70B
0x2b4c9  ldloc.3
0x2b4ca  ldloc.2
0x2b4cb  ldelem.u2
0x2b4cc  ldc.i4.s 0x5B
0x2b4ce  bne.un   loc_2B554
0x2b4d3  ldarg.0
0x2b4d4  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b4d9  ldc.i4.s 9
0x2b4db  beq.s    loc_2B539
0x2b4dd  ldloc.2
0x2b4de  ldc.i4.1
0x2b4df  add
0x2b4e0  stloc.2
0x2b4e1  ldarg.0
0x2b4e2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b4e7  ldfld    int32 ParsingState::charsUsed
0x2b4ec  ldloc.2
0x2b4ed  sub
0x2b4ee  ldc.i4.6
0x2b4ef  blt      loc_2B70B
0x2b4f4  ldloc.3
0x2b4f5  ldloc.2
0x2b4f6  ldc.i4.6
0x2b4f7  ldstr    aCdata// "CDATA["
0x2b4fc  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x2b501  brfalse.s loc_2B528
0x2b503  ldarg.0
0x2b504  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b509  ldloc.2
0x2b50a  ldc.i4.6
0x2b50b  add
0x2b50c  stfld    int32 ParsingState::charPos
0x2b511  ldarg.0
0x2b512  call     instance void System.Xml.XmlTextReaderImpl::ParseCData()
0x2b517  ldarg.0
0x2b518  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b51d  brtrue.s loc_2B526
0x2b51f  ldarg.0
0x2b520  ldc.i4.1
0x2b521  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b526  ldc.i4.1
0x2b527  ret
0x2b528  ldarg.0
0x2b529  ldloc.2
0x2b52a  ldstr    aCdata// "CDATA["
0x2b52f  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x2b534  br       loc_2B70B
0x2b539  ldarg.0
0x2b53a  ldarg.0
0x2b53b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b540  ldfld    int32 ParsingState::charPos
0x2b545  ldstr    aXmlInvalidroot// "Xml_InvalidRootData"
0x2b54a  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2b54f  br       loc_2B70B
0x2b554  ldarg.0
0x2b555  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b55a  ldc.i4.s 9
0x2b55c  beq.s    loc_2B566
0x2b55e  ldarg.0
0x2b55f  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b564  brtrue.s loc_2B587
0x2b566  ldarg.0
0x2b567  ldc.i4.s 9
0x2b569  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b56e  ldarg.0
0x2b56f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b574  ldloc.2
0x2b575  stfld    int32 ParsingState::charPos
0x2b57a  ldarg.0
0x2b57b  call     instance bool System.Xml.XmlTextReaderImpl::ParseDoctypeDecl()
0x2b580  brfalse  loc_2B402
0x2b585  ldc.i4.1
0x2b586  ret
0x2b587  ldarg.0
0x2b588  ldloc.2
0x2b589  call     instance string System.Xml.XmlTextReaderImpl::ParseUnexpectedToken(int32 pos)
0x2b58e  ldstr    aDoctype_0// "DOCTYPE"
0x2b593  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2b598  brfalse.s loc_2B5AA
0x2b59a  ldarg.0
0x2b59b  ldstr    aXmlBaddtdlocat// "Xml_BadDTDLocation"
0x2b5a0  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x2b5a5  br       loc_2B70B
0x2b5aa  ldarg.0
0x2b5ab  ldloc.2
0x2b5ac  ldstr    asc_12B44E// "<!--"
0x2b5b1  ldstr    aCdata_0// "<[CDATA["
0x2b5b6  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x2b5bb  br       loc_2B70B
0x2b5c0  ldarg.0
0x2b5c1  ldloc.2
0x2b5c2  ldc.i4.1
0x2b5c3  add
0x2b5c4  ldstr    aXmlUnexpectede_1// "Xml_UnexpectedEndTag"
0x2b5c9  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2b5ce  br       loc_2B70B
0x2b5d3  ldarg.0
0x2b5d4  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x2b5d9  brfalse.s loc_2B600
0x2b5db  ldarg.0
0x2b5dc  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b5e1  ldc.i4.s 9
0x2b5e3  bne.un.s loc_2B5F1
0x2b5e5  ldarg.0
0x2b5e6  ldloc.2
0x2b5e7  ldstr    aXmlMultipleroo// "Xml_MultipleRoots"
0x2b5ec  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2b5f1  ldarg.0
0x2b5f2  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b5f7  brtrue.s loc_2B600
0x2b5f9  ldarg.0
0x2b5fa  ldc.i4.1
0x2b5fb  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b600  ldarg.0
0x2b601  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b606  ldloc.2
0x2b607  stfld    int32 ParsingState::charPos
0x2b60c  ldarg.0
0x2b60d  ldc.i4.1
0x2b60e  stfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x2b613  ldarg.0
0x2b614  call     instance void System.Xml.XmlTextReaderImpl::ParseElement()
0x2b619  ldc.i4.1
0x2b61a  ret
0x2b61b  ldloc.3
0x2b61c  ldloc.2
0x2b61d  ldelem.u2
0x2b61e  ldc.i4.s 0x26
0x2b620  bne.un   loc_2B6AD
0x2b625  ldarg.0
0x2b626  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b62b  ldc.i4.s 9
0x2b62d  bne.un.s loc_2B640
0x2b62f  ldarg.0
0x2b630  ldloc.2
0x2b631  ldstr    aXmlInvalidroot// "Xml_InvalidRootData"
0x2b636  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2b63b  br       loc_2B70B
0x2b640  ldarg.0
0x2b641  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b646  brtrue.s loc_2B64F
0x2b648  ldarg.0
0x2b649  ldc.i4.1
0x2b64a  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b64f  ldarg.0
0x2b650  ldc.i4.0
0x2b651  ldc.i4.1
0x2b652  ldloca.s 5
0x2b654  call     instance valuetype EntityType System.Xml.XmlTextReaderImpl::HandleEntityReference(bool isInAttributeValue, valuetype EntityExpandType expandType, [out] int32& charRefEndPos)
0x2b659  stloc.s  6
0x2b65b  ldloc.s  6
0x2b65d  ldc.i4.2
0x2b65e  ble.un.s loc_2B683
0x2b660  ldloc.s  6
0x2b662  ldc.i4.6
0x2b663  bne.un.s loc_2B690
0x2b665  ldarg.0
0x2b666  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2b66b  ldc.i4.s 0xD
0x2b66d  bne.un.s loc_2B67B
0x2b66f  ldarg.0
0x2b670  ldarg.0
0x2b671  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x2b676  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x2b67b  ldarg.0
0x2b67c  call     instance void System.Xml.XmlTextReaderImpl::ParseEntityReference()
0x2b681  ldc.i4.1
0x2b682  ret
0x2b683  ldarg.0
0x2b684  call     instance bool System.Xml.XmlTextReaderImpl::ParseText()
0x2b689  brfalse  loc_2B402
0x2b68e  ldc.i4.1
0x2b68f  ret
0x2b690  ldarg.0
0x2b691  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b696  ldfld    char[] ParsingState::chars
0x2b69b  stloc.3
0x2b69c  ldarg.0
0x2b69d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b6a2  ldfld    int32 ParsingState::charPos
0x2b6a7  stloc.2
0x2b6a8  br       loc_2B402
0x2b6ad  ldloc.2
0x2b6ae  ldarg.0
0x2b6af  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2b6b4  ldfld    int32 ParsingState::charsUsed
0x2b6b9  beq.s    loc_2B70B
0x2b6bb  ldarg.0
0x2b6bc  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x2b6c1  ldloc.0
0x2b6c2  or
0x2b6c3  brfalse.s loc_2B6CA
0x2b6c5  ldloc.3
0x2b6c6  ldloc.2
0x2b6c7  ldelem.u2
0x2b6c8  brfalse.s loc_2B70B
0x2b6ca  ldarg.0
0x2b6cb  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x2b6d0  ldc.i4.s 9
0x2b6d2  bne.un.s loc_2B6E1
0x2b6d4  ldarg.0
0x2b6d5  call     instance bool System.Xml.XmlTextReaderImpl::ParseRootLevelWhitespace()
0x2b6da  brfalse  loc_2B402
0x2b6df  ldc.i4.1
0x2b6e0  ret
  ... truncated ...
```
