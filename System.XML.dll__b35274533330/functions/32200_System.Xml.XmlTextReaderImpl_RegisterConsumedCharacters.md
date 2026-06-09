# System.Xml.XmlTextReaderImpl::RegisterConsumedCharacters

- ea: `0x32200`
- end: `0x322ab`
- name: `System.Xml.XmlTextReaderImpl::RegisterConsumedCharacters`
- size: `171`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x29620`
- `0x2a510`
- `0x303c0`
- `0x30480`
- `0x1013c0`
- `0x10abb0`

## callees

- `0x298b0`
- `0x32200`

## string_xrefs

- `0x3221d`: `Xml_LimitExceeded`
- `0x32244`: `Xml_LimitExceeded`
- `0x32274`: `Xml_LimitExceeded`
- `0x3229b`: `Xml_LimitExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x32200  ldarg.0
0x32201  ldfld    int64 System.Xml.XmlTextReaderImpl::maxCharactersInDocument
0x32206  ldc.i4.0
0x32207  conv.i8
0x32208  ble.s    loc_32253
0x3220a  ldarg.0
0x3220b  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersInDocument
0x32210  ldarg.1
0x32211  add
0x32212  stloc.0
0x32213  ldloc.0
0x32214  ldarg.0
0x32215  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersInDocument
0x3221a  bge.s    loc_3222E
0x3221c  ldarg.0
0x3221d  ldstr    aXmlLimitexceed// "Xml_LimitExceeded"
0x32222  ldstr    aMaxcharactersi// "MaxCharactersInDocument"
0x32227  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string arg)
0x3222c  br.s     loc_32235
0x3222e  ldarg.0
0x3222f  ldloc.0
0x32230  stfld    int64 System.Xml.XmlTextReaderImpl::charactersInDocument
0x32235  ldarg.0
0x32236  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersInDocument
0x3223b  ldarg.0
0x3223c  ldfld    int64 System.Xml.XmlTextReaderImpl::maxCharactersInDocument
0x32241  ble.s    loc_32253
0x32243  ldarg.0
0x32244  ldstr    aXmlLimitexceed// "Xml_LimitExceeded"
0x32249  ldstr    aMaxcharactersi// "MaxCharactersInDocument"
0x3224e  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string arg)
0x32253  ldarg.0
0x32254  ldfld    int64 System.Xml.XmlTextReaderImpl::maxCharactersFromEntities
0x32259  ldc.i4.0
0x3225a  conv.i8
0x3225b  cgt
0x3225d  ldarg.2
0x3225e  and
0x3225f  brfalse.s loc_322AA
0x32261  ldarg.0
0x32262  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersFromEntities
0x32267  ldarg.1
0x32268  add
0x32269  stloc.1
0x3226a  ldloc.1
0x3226b  ldarg.0
0x3226c  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersFromEntities
0x32271  bge.s    loc_32285
0x32273  ldarg.0
0x32274  ldstr    aXmlLimitexceed// "Xml_LimitExceeded"
0x32279  ldstr    aMaxcharactersf// "MaxCharactersFromEntities"
0x3227e  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string arg)
0x32283  br.s     loc_3228C
0x32285  ldarg.0
0x32286  ldloc.1
0x32287  stfld    int64 System.Xml.XmlTextReaderImpl::charactersFromEntities
0x3228c  ldarg.0
0x3228d  ldfld    int64 System.Xml.XmlTextReaderImpl::charactersFromEntities
0x32292  ldarg.0
0x32293  ldfld    int64 System.Xml.XmlTextReaderImpl::maxCharactersFromEntities
0x32298  ble.s    loc_322AA
0x3229a  ldarg.0
0x3229b  ldstr    aXmlLimitexceed// "Xml_LimitExceeded"
0x322a0  ldstr    aMaxcharactersf// "MaxCharactersFromEntities"
0x322a5  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string arg)
0x322aa  ret
```
