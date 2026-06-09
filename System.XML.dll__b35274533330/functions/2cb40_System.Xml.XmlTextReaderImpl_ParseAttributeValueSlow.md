# System.Xml.XmlTextReaderImpl::ParseAttributeValueSlow

- ea: `0x2cb40`
- end: `0x2d20c`
- name: `System.Xml.XmlTextReaderImpl::ParseAttributeValueSlow`
- size: `1740`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x2c2b0`
- `0x30f90`

## callees

- `0xe360`
- `0xe370`
- `0xf0f0`
- `0xf110`
- `0x12940`
- `0x15c10`
- `0x29700`
- `0x29740`
- `0x298f0`
- `0x2a510`
- `0x2cb40`
- `0x2d210`
- `0x2dd60`
- `0x2e0a0`
- `0x2e0b0`
- `0x2fc60`
- `0x2ff90`
- `0xfe500`
- `0xfe510`
- `0xfe920`
- `0xfead0`
- `0xfeb20`
- `0xfeb70`

## string_xrefs

- `0x2d126`: `Xml_InternalError`
- `0x2d112`: `Xml_UnclosedQuote`
- `0x2d0d3`: `Xml_UnexpectedEOF1`
- `0x2cd62`: `Xml_BadAttributeChar`
- `0x2d105`: `Xml_EntityRefNesting`

## pseudocode

```c

```

## disassembly

```asm
0x2cb40  ldarg.1
0x2cb41  stloc.0
0x2cb42  ldarg.0
0x2cb43  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cb48  ldfld    char[] ParsingState::chars
0x2cb4d  stloc.1
0x2cb4e  ldarg.0
0x2cb4f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cb54  ldfld    int32 ParsingState::entityId
0x2cb59  stloc.2
0x2cb5a  ldc.i4.0
0x2cb5b  stloc.3
0x2cb5c  ldloca.s 4
0x2cb5e  ldarg.0
0x2cb5f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cb64  ldfld    int32 ParsingState::lineNo
0x2cb69  ldarg.0
0x2cb6a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cb6f  call     instance int32 ParsingState::get_LinePos()
0x2cb74  call     instance void System.Xml.LineInfo::.ctor(int32 lineNo, int32 linePos)
0x2cb79  ldnull
0x2cb7a  stloc.s  5
0x2cb7c  br.s     loc_2CB82
0x2cb7e  ldloc.0
0x2cb7f  ldc.i4.1
0x2cb80  add
0x2cb81  stloc.0
0x2cb82  ldarg.0
0x2cb83  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2cb88  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x2cb8d  ldloc.1
0x2cb8e  ldloc.0
0x2cb8f  ldelem.u2
0x2cb90  add
0x2cb91  ldind.u1
0x2cb92  ldc.i4   0x80
0x2cb97  and
0x2cb98  brtrue.s loc_2CB7E
0x2cb9a  ldloc.0
0x2cb9b  ldarg.0
0x2cb9c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cba1  ldfld    int32 ParsingState::charPos
0x2cba6  sub
0x2cba7  ldc.i4.0
0x2cba8  ble.s    loc_2CBDB
0x2cbaa  ldarg.0
0x2cbab  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cbb0  ldloc.1
0x2cbb1  ldarg.0
0x2cbb2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cbb7  ldfld    int32 ParsingState::charPos
0x2cbbc  ldloc.0
0x2cbbd  ldarg.0
0x2cbbe  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cbc3  ldfld    int32 ParsingState::charPos
0x2cbc8  sub
0x2cbc9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2cbce  pop
0x2cbcf  ldarg.0
0x2cbd0  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cbd5  ldloc.0
0x2cbd6  stfld    int32 ParsingState::charPos
0x2cbdb  ldloc.1
0x2cbdc  ldloc.0
0x2cbdd  ldelem.u2
0x2cbde  ldarg.2
0x2cbdf  bne.un.s loc_2CBF2
0x2cbe1  ldloc.2
0x2cbe2  ldarg.0
0x2cbe3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cbe8  ldfld    int32 ParsingState::entityId
0x2cbed  beq      loc_2D184
0x2cbf2  ldloc.1
0x2cbf3  ldloc.0
0x2cbf4  ldelem.u2
0x2cbf5  stloc.s  8
0x2cbf7  ldloc.s  8
0x2cbf9  ldc.i4.s 0x26
0x2cbfb  bgt.un.s loc_2CC32
0x2cbfd  ldloc.s  8
0x2cbff  ldc.i4.s 9
0x2cc01  sub
0x2cc02  switch   loc_2CD25, loc_2CC52, loc_2D039, loc_2D039, loc_2CC8B
0x2cc1b  ldloc.s  8
0x2cc1d  ldc.i4.s 0x22
0x2cc1f  beq      loc_2CD57
0x2cc24  ldloc.s  8
0x2cc26  ldc.i4.s 0x26
0x2cc28  beq      loc_2CD79
0x2cc2d  br       loc_2D039
0x2cc32  ldloc.s  8
0x2cc34  ldc.i4.s 0x27
0x2cc36  beq      loc_2CD57
0x2cc3b  ldloc.s  8
0x2cc3d  ldc.i4.s 0x3C
0x2cc3f  beq      loc_2CD60
0x2cc44  ldloc.s  8
0x2cc46  ldc.i4.s 0x3E
0x2cc48  beq      loc_2CD57
0x2cc4d  br       loc_2D039
0x2cc52  ldloc.0
0x2cc53  ldc.i4.1
0x2cc54  add
0x2cc55  stloc.0
0x2cc56  ldarg.0
0x2cc57  ldloc.0
0x2cc58  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x2cc5d  ldarg.0
0x2cc5e  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2cc63  brfalse  loc_2CB82
0x2cc68  ldarg.0
0x2cc69  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cc6e  ldc.i4.s 0x20
0x2cc70  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2cc75  pop
0x2cc76  ldarg.0
0x2cc77  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cc7c  ldflda   int32 ParsingState::charPos
0x2cc81  dup
0x2cc82  ldind.i4
0x2cc83  ldc.i4.1
0x2cc84  add
0x2cc85  stind.i4
0x2cc86  br       loc_2CB82
0x2cc8b  ldloc.1
0x2cc8c  ldloc.0
0x2cc8d  ldc.i4.1
0x2cc8e  add
0x2cc8f  ldelem.u2
0x2cc90  ldc.i4.s 0xA
0x2cc92  bne.un.s loc_2CCD3
0x2cc94  ldloc.0
0x2cc95  ldc.i4.2
0x2cc96  add
0x2cc97  stloc.0
0x2cc98  ldarg.0
0x2cc99  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2cc9e  brfalse.s loc_2CD19
0x2cca0  ldarg.0
0x2cca1  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cca6  ldarg.0
0x2cca7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ccac  ldfld    bool ParsingState::eolNormalized
0x2ccb1  brtrue.s loc_2CCBA
0x2ccb3  ldstr    asc_129382// " "
0x2ccb8  br.s     loc_2CCBF
0x2ccba  ldstr    asc_129468// "  "
0x2ccbf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ccc4  pop
0x2ccc5  ldarg.0
0x2ccc6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cccb  ldloc.0
0x2cccc  stfld    int32 ParsingState::charPos
0x2ccd1  br.s     loc_2CD19
0x2ccd3  ldloc.0
0x2ccd4  ldc.i4.1
0x2ccd5  add
0x2ccd6  ldarg.0
0x2ccd7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ccdc  ldfld    int32 ParsingState::charsUsed
0x2cce1  blt.s    loc_2CCF3
0x2cce3  ldarg.0
0x2cce4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cce9  ldfld    bool ParsingState::isEof
0x2ccee  brfalse  loc_2D08F
0x2ccf3  ldloc.0
0x2ccf4  ldc.i4.1
0x2ccf5  add
0x2ccf6  stloc.0
0x2ccf7  ldarg.0
0x2ccf8  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2ccfd  brfalse.s loc_2CD19
0x2ccff  ldarg.0
0x2cd00  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cd05  ldc.i4.s 0x20
0x2cd07  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2cd0c  pop
0x2cd0d  ldarg.0
0x2cd0e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cd13  ldloc.0
0x2cd14  stfld    int32 ParsingState::charPos
0x2cd19  ldarg.0
0x2cd1a  ldloc.0
0x2cd1b  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x2cd20  br       loc_2CB82
0x2cd25  ldloc.0
0x2cd26  ldc.i4.1
0x2cd27  add
0x2cd28  stloc.0
0x2cd29  ldarg.0
0x2cd2a  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2cd2f  brfalse  loc_2CB82
0x2cd34  ldarg.0
0x2cd35  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cd3a  ldc.i4.s 0x20
0x2cd3c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2cd41  pop
0x2cd42  ldarg.0
0x2cd43  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cd48  ldflda   int32 ParsingState::charPos
0x2cd4d  dup
0x2cd4e  ldind.i4
0x2cd4f  ldc.i4.1
0x2cd50  add
0x2cd51  stind.i4
0x2cd52  br       loc_2CB82
0x2cd57  ldloc.0
0x2cd58  ldc.i4.1
0x2cd59  add
0x2cd5a  stloc.0
0x2cd5b  br       loc_2CB82
0x2cd60  ldarg.0
0x2cd61  ldloc.0
0x2cd62  ldstr    aXmlBadattribut// "Xml_BadAttributeChar"
0x2cd67  ldc.i4.s 0x3C
0x2cd69  ldc.i4.0
0x2cd6a  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x2cd6f  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2cd74  br       loc_2D08F
0x2cd79  ldloc.0
0x2cd7a  ldarg.0
0x2cd7b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cd80  ldfld    int32 ParsingState::charPos
0x2cd85  sub
0x2cd86  ldc.i4.0
0x2cd87  ble.s    loc_2CDAE
0x2cd89  ldarg.0
0x2cd8a  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2cd8f  ldloc.1
0x2cd90  ldarg.0
0x2cd91  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cd96  ldfld    int32 ParsingState::charPos
0x2cd9b  ldloc.0
0x2cd9c  ldarg.0
0x2cd9d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cda2  ldfld    int32 ParsingState::charPos
0x2cda7  sub
0x2cda8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2cdad  pop
0x2cdae  ldarg.0
0x2cdaf  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cdb4  ldloc.0
0x2cdb5  stfld    int32 ParsingState::charPos
0x2cdba  ldarg.0
0x2cdbb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cdc0  ldfld    int32 ParsingState::entityId
0x2cdc5  stloc.s  6
0x2cdc7  ldloca.s 7
0x2cdc9  ldarg.0
0x2cdca  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cdcf  ldfld    int32 ParsingState::lineNo
0x2cdd4  ldarg.0
0x2cdd5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2cdda  call     instance int32 ParsingState::get_LinePos()
0x2cddf  ldc.i4.1
0x2cde0  add
0x2cde1  call     instance void System.Xml.LineInfo::.ctor(int32 lineNo, int32 linePos)
0x2cde6  ldarg.0
0x2cde7  ldc.i4.1
0x2cde8  ldc.i4.0
0x2cde9  ldloca.s 0
0x2cdeb  call     instance valuetype EntityType System.Xml.XmlTextReaderImpl::HandleEntityReference(bool isInAttributeValue, valuetype EntityExpandType expandType, [out] int32& charRefEndPos)
0x2cdf0  stloc.s  9
0x2cdf2  ldloc.s  9
0x2cdf4  switch   loc_2D028, loc_2D028, loc_2D028, loc_2D01C, loc_2D01C, loc_2D01C, loc_2CE1E, loc_2CF5E
0x2ce19  br       loc_2D01C
0x2ce1e  ldarg.0
0x2ce1f  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x2ce24  brtrue   loc_2CF36
0x2ce29  ldarg.0
0x2ce2a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2ce2f  ldfld    int32 ParsingState::entityId
0x2ce34  ldloc.2
0x2ce35  bne.un   loc_2CF36
0x2ce3a  ldarg.0
0x2ce3b  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2ce40  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2ce45  ldloc.3
0x2ce46  sub
0x2ce47  stloc.s  0xA
0x2ce49  ldloc.s  0xA
0x2ce4b  ldc.i4.0
0x2ce4c  ble.s    loc_2CE8E
0x2ce4e  newobj   instance void NodeData::.ctor()
0x2ce53  stloc.s  0xD
0x2ce55  ldloc.s  0xD
0x2ce57  ldloc.s  4
0x2ce59  stfld    valuetype System.Xml.LineInfo NodeData::lineInfo
0x2ce5e  ldloc.s  0xD
0x2ce60  ldarg.3
0x2ce61  ldfld    int32 NodeData::depth
0x2ce66  ldc.i4.1
0x2ce67  add
0x2ce68  stfld    int32 NodeData::depth
0x2ce6d  ldloc.s  0xD
0x2ce6f  ldc.i4.3
0x2ce70  ldarg.0
0x2ce71  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x2ce76  ldloc.3
0x2ce77  ldloc.s  0xA
  ... truncated ...
```
