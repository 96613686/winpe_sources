# System.Windows.Markup.MarkupExtensionParser::TokenizeAttributes

- ea: `0xac0a0`
- end: `0xac534`
- name: `System.Windows.Markup.MarkupExtensionParser::TokenizeAttributes`
- size: `1172`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xab850`
- `0xabda0`
- `0xabfb0`

## callees

- `0xac0a0`
- `0xac540`
- `0xac580`
- `0xac960`
- `0xacc00`
- `0xacc20`
- `0xad000`
- `0x2511e0`
- `0x251200`
- `0x251220`

## string_xrefs

- `0xac29c`: `ParserMarkupExtensionInvalidClosingBracketCharacers`
- `0xac31a`: `ParserMarkupExtensionNoQuotesInName`
- `0xac390`: `ParserMarkupExtensionMalformedBracketCharacers`
- `0xac3b7`: `ParserMarkupExtensionDelimiterBeforeFirstAttribute`
- `0xac3de`: `ParserMarkupExtensionBadDelimiter`
- `0xac47e`: `ParserMarkupExtensionBadDelimiter`
- `0xac4f9`: `ParserMarkupExtensionNoEndCurlie`
- `0xac513`: `ParserMarkupExtensionTrailingGarbage`

## pseudocode

```c

```

## disassembly

```asm
0xac0a0  ldarg.s  4
0xac0a2  ldtoken  UnknownMarkupExtension
0xac0a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xac0ac  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xac0b1  brfalse.s loc_AC0B5
0xac0b3  ldnull
0xac0b4  ret
0xac0b5  ldc.i4.0
0xac0b6  stloc.0
0xac0b7  ldarg.0
0xac0b8  ldarg.s  4
0xac0ba  ldloca.s 0
0xac0bc  call     instance class [mscorlib]System.Reflection.ParameterInfo[] System.Windows.Markup.MarkupExtensionParser::FindLongestConstructor(class [mscorlib]System.Type extensionType, [out] int32& maxConstructorArguments)
0xac0c1  stloc.1
0xac0c2  ldarg.0
0xac0c3  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.MarkupExtensionParser::_parserContext
0xac0c8  ldarg.s  4
0xac0ca  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class MS.Internal.Xaml.Parser.SpecialBracketCharacters> System.Windows.Markup.ParserContext::InitBracketCharacterCacheForType(class [mscorlib]System.Type type)
0xac0cf  stloc.2
0xac0d0  newobj   instance void class [System]System.Collections.Generic.Stack`1<char>::.ctor()
0xac0d5  stloc.3
0xac0d6  ldc.i4.0
0xac0d7  stloc.s  4
0xac0d9  ldloc.1
0xac0da  brfalse.s loc_AC0E2
0xac0dc  ldloc.0
0xac0dd  ldc.i4.0
0xac0de  cgt
0xac0e0  br.s     loc_AC0E3
0xac0e2  ldc.i4.0
0xac0e3  stloc.s  5
0xac0e5  ldc.i4.0
0xac0e6  stloc.s  6
0xac0e8  ldnull
0xac0e9  stloc.s  7
0xac0eb  ldarg.1
0xac0ec  callvirt instance int32 [mscorlib]System.String::get_Length()
0xac0f1  stloc.s  8
0xac0f3  ldc.i4.0
0xac0f4  stloc.s  9
0xac0f6  ldc.i4.0
0xac0f7  stloc.s  0xA
0xac0f9  ldc.i4.0
0xac0fa  stloc.s  0xB
0xac0fc  ldc.i4.0
0xac0fd  stloc.s  0xC
0xac0ff  ldc.i4.s 0x27
0xac101  stloc.s  0xD
0xac103  ldc.i4.0
0xac104  stloc.s  0xE
0xac106  ldnull
0xac107  stloc.s  0xF
0xac109  ldc.i4.0
0xac10a  stloc.s  0x10
0xac10c  ldnull
0xac10d  stloc.s  0x11
0xac10f  ldnull
0xac110  stloc.s  0x12
0xac112  ldloc.s  5
0xac114  brfalse.s loc_AC13F
0xac116  ldloc.2
0xac117  brfalse.s loc_AC13F
0xac119  ldloc.0
0xac11a  ldc.i4.0
0xac11b  bgt.s    loc_AC120
0xac11d  ldnull
0xac11e  br.s     loc_AC129
0xac120  ldloc.1
0xac121  ldloc.s  4
0xac123  ldelem.ref
0xac124  callvirt instance string [mscorlib]System.Reflection.ParameterInfo::get_Name()
0xac129  stloc.s  0x11
0xac12b  ldloc.s  0x11
0xac12d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xac132  brtrue.s loc_AC13F
0xac134  ldarg.0
0xac135  ldloc.s  0x11
0xac137  ldloc.2
0xac138  call     instance class MS.Internal.Xaml.Parser.SpecialBracketCharacters System.Windows.Markup.MarkupExtensionParser::GetBracketCharacterForProperty(string propertyName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class MS.Internal.Xaml.Parser.SpecialBracketCharacters> bracketCharacterCache)
0xac13d  stloc.s  0x12
0xac13f  ldc.i4.0
0xac140  stloc.s  0x10
0xac142  br       loc_AC4E7
0xac147  ldloc.s  0xA
0xac149  brtrue.s loc_AC15F
0xac14b  ldarg.1
0xac14c  ldloc.s  0x10
0xac14e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac153  ldc.i4.s 0x5C
0xac155  bne.un.s loc_AC15F
0xac157  ldc.i4.1
0xac158  stloc.s  0xA
0xac15a  br       loc_AC4E1
0xac15f  ldloc.s  0xB
0xac161  brtrue.s loc_AC175
0xac163  ldarg.1
0xac164  ldloc.s  0x10
0xac166  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac16b  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0xac170  brtrue.s loc_AC175
0xac172  ldc.i4.1
0xac173  stloc.s  0xB
0xac175  ldloc.s  9
0xac177  brtrue.s loc_AC180
0xac179  ldloc.s  0xE
0xac17b  ldc.i4.0
0xac17c  cgt
0xac17e  br.s     loc_AC181
0xac180  ldc.i4.1
0xac181  ldloc.s  0xB
0xac183  or
0xac184  brfalse  loc_AC4E1
0xac189  ldloc.s  0xF
0xac18b  brtrue.s loc_AC19E
0xac18d  ldloc.s  8
0xac18f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xac194  stloc.s  0xF
0xac196  ldc.i4.1
0xac197  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0xac19c  stloc.s  7
0xac19e  ldloc.s  0xA
0xac1a0  brfalse.s loc_AC1C4
0xac1a2  ldloc.s  0xF
0xac1a4  ldc.i4.s 0x5C
0xac1a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xac1ab  pop
0xac1ac  ldloc.s  0xF
0xac1ae  ldarg.1
0xac1af  ldloc.s  0x10
0xac1b1  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac1b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xac1bb  pop
0xac1bc  ldc.i4.0
0xac1bd  stloc.s  0xA
0xac1bf  br       loc_AC4E1
0xac1c4  ldloc.s  9
0xac1c6  brtrue.s loc_AC1CD
0xac1c8  ldloc.s  0xE
0xac1ca  ldc.i4.0
0xac1cb  ble.s    loc_AC232
0xac1cd  ldloc.s  9
0xac1cf  brfalse.s loc_AC1F2
0xac1d1  ldarg.1
0xac1d2  ldloc.s  0x10
0xac1d4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac1d9  ldloc.s  0xD
0xac1db  bne.un.s loc_AC1F2
0xac1dd  ldc.i4.0
0xac1de  stloc.s  9
0xac1e0  ldc.i4.0
0xac1e1  stloc.s  0xB
0xac1e3  ldloc.s  7
0xac1e5  ldloc.s  0xF
0xac1e7  ldc.i4.0
0xac1e8  call     void System.Windows.Markup.MarkupExtensionParser::AddToTokenList(class [mscorlib]System.Collections.ArrayList list, class [mscorlib]System.Text.StringBuilder sb, bool trim)
0xac1ed  br       loc_AC4E1
0xac1f2  ldloc.s  0xE
0xac1f4  ldc.i4.0
0xac1f5  ble.s    loc_AC20B
0xac1f7  ldarg.1
0xac1f8  ldloc.s  0x10
0xac1fa  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac1ff  ldc.i4.s 0x7D
0xac201  bne.un.s loc_AC20B
0xac203  ldloc.s  0xE
0xac205  ldc.i4.1
0xac206  sub
0xac207  stloc.s  0xE
0xac209  br.s     loc_AC21D
0xac20b  ldarg.1
0xac20c  ldloc.s  0x10
0xac20e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac213  ldc.i4.s 0x7B
0xac215  bne.un.s loc_AC21D
0xac217  ldloc.s  0xE
0xac219  ldc.i4.1
0xac21a  add
0xac21b  stloc.s  0xE
0xac21d  ldloc.s  0xF
0xac21f  ldarg.1
0xac220  ldloc.s  0x10
0xac222  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac227  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xac22c  pop
0xac22d  br       loc_AC4E1
0xac232  ldloc.s  6
0xac234  brfalse  loc_AC2CC
0xac239  ldloc.s  0xF
0xac23b  ldarg.1
0xac23c  ldloc.s  0x10
0xac23e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac243  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xac248  pop
0xac249  ldloc.s  0x12
0xac24b  ldarg.1
0xac24c  ldloc.s  0x10
0xac24e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac253  callvirt instance bool MS.Internal.Xaml.Parser.SpecialBracketCharacters::StartsEscapeSequence(char ch)
0xac258  brfalse.s loc_AC26A
0xac25a  ldloc.3
0xac25b  ldarg.1
0xac25c  ldloc.s  0x10
0xac25e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac263  callvirt instance void class [System]System.Collections.Generic.Stack`1<char>::Push(var<u1>)
0xac268  br.s     loc_AC2B9
0xac26a  ldloc.s  0x12
0xac26c  ldarg.1
0xac26d  ldloc.s  0x10
0xac26f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac274  callvirt instance bool MS.Internal.Xaml.Parser.SpecialBracketCharacters::EndsEscapeSequence(char ch)
0xac279  brfalse.s loc_AC2B9
0xac27b  ldloc.s  0x12
0xac27d  ldloc.3
0xac27e  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<char>::Peek()
0xac283  ldarg.1
0xac284  ldloc.s  0x10
0xac286  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac28b  callvirt instance bool MS.Internal.Xaml.Parser.SpecialBracketCharacters::Match(char start, char end)
0xac290  brfalse.s loc_AC29B
0xac292  ldloc.3
0xac293  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<char>::Pop()
0xac298  pop
0xac299  br.s     loc_AC2B9
0xac29b  ldarg.0
0xac29c  ldstr    aParsermarkupex// "ParserMarkupExtensionInvalidClosingBrac"...
0xac2a1  ldarg.1
0xac2a2  ldloc.s  0x10
0xac2a4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac2a9  stloc.s  0x13
0xac2ab  ldloca.s 0x13
0xac2ad  call     instance string [mscorlib]System.Char::ToString()
0xac2b2  ldarg.2
0xac2b3  ldarg.3
0xac2b4  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, int32 lineNumber, int32 linePosition)
0xac2b9  ldloc.3
0xac2ba  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<char>::get_Count()
0xac2bf  brtrue   loc_AC4E1
0xac2c4  ldc.i4.0
0xac2c5  stloc.s  6
0xac2c7  br       loc_AC4E1
0xac2cc  ldarg.1
0xac2cd  ldloc.s  0x10
0xac2cf  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac2d4  stloc.s  0x14
0xac2d6  ldloc.s  0x14
0xac2d8  ldc.i4.s 0x2C
0xac2da  bgt.un.s loc_AC2F3
0xac2dc  ldloc.s  0x14
0xac2de  ldc.i4.s 0x22
0xac2e0  beq.s    loc_AC310
0xac2e2  ldloc.s  0x14
0xac2e4  ldc.i4.s 0x27
0xac2e6  beq.s    loc_AC310
0xac2e8  ldloc.s  0x14
0xac2ea  ldc.i4.s 0x2C
0xac2ec  beq.s    loc_AC339
0xac2ee  br       loc_AC4A5
0xac2f3  ldloc.s  0x14
0xac2f5  ldc.i4.s 0x3D
0xac2f7  beq.s    loc_AC339
0xac2f9  ldloc.s  0x14
0xac2fb  ldc.i4.s 0x7B
0xac2fd  beq      loc_AC48D
0xac302  ldloc.s  0x14
0xac304  ldc.i4.s 0x7D
0xac306  beq      loc_AC439
0xac30b  br       loc_AC4A5
0xac310  ldloc.s  0xF
0xac312  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0xac317  brfalse.s loc_AC327
0xac319  ldarg.0
0xac31a  ldstr    aParsermarkupex_0// "ParserMarkupExtensionNoQuotesInName"
0xac31f  ldarg.1
0xac320  ldarg.2
0xac321  ldarg.3
0xac322  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, int32 lineNumber, int32 linePosition)
0xac327  ldc.i4.1
0xac328  stloc.s  9
0xac32a  ldarg.1
0xac32b  ldloc.s  0x10
0xac32d  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac332  stloc.s  0xD
0xac334  br       loc_AC4E1
0xac339  ldloc.s  5
0xac33b  brfalse.s loc_AC36F
0xac33d  ldarg.1
0xac33e  ldloc.s  0x10
0xac340  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xac345  ldc.i4.s 0x2C
0xac347  bne.un.s loc_AC36F
0xac349  ldloc.s  4
0xac34b  ldc.i4.1
0xac34c  add
0xac34d  dup
0xac34e  stloc.s  4
0xac350  ldloc.0
0xac351  clt
0xac353  stloc.s  5
0xac355  ldloc.s  5
0xac357  brfalse.s loc_AC36F
  ... truncated ...
```
