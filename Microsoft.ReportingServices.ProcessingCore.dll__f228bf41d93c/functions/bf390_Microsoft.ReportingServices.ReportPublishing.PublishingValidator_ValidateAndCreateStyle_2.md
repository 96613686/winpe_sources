# Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle_2

- ea: `0xbf390`
- end: `0xc00c1`
- name: `Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle_2`
- size: `3377`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0xbf360`
- `0xbf370`
- `0xbf380`

## callees

- `0xbe810`
- `0xbe860`
- `0xbe9a0`
- `0xbebd0`
- `0xbec20`
- `0xbecb0`
- `0xbed80`
- `0xbedd0`
- `0xbee20`
- `0xbee70`
- `0xbeed0`
- `0xbef20`
- `0xbef70`
- `0xbefe0`
- `0xbf030`
- `0xbf080`
- `0xbf0d0`
- `0xbf120`
- `0xbf170`
- `0xbf1c0`
- `0xbf210`
- `0xbf260`
- `0xbf2b0`
- `0xbf390`
- `0x117b10`
- `0x133570`
- `0x133590`
- `0x133f80`

## pseudocode

```c

```

## disassembly

```asm
0xbf390  ldarg.s  6
0xbf392  ldc.i4.0
0xbf393  stind.i1
0xbf394  ldc.i4.0
0xbf395  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.ConstructionPhase phase)
0xbf39a  stloc.0
0xbf39b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xbf3a0  ldarg.0
0xbf3a1  ldnull
0xbf3a2  cgt.un
0xbf3a4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xbf3a9  ldnull
0xbf3aa  stloc.1
0xbf3ab  ldnull
0xbf3ac  stloc.2
0xbf3ad  ldnull
0xbf3ae  stloc.3
0xbf3af  ldnull
0xbf3b0  stloc.s  4
0xbf3b2  ldc.i4.0
0xbf3b3  stloc.s  5
0xbf3b5  br       loc_C0093
0xbf3ba  ldarg.0
0xbf3bb  ldloc.s  5
0xbf3bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute>::get_Item(!!T0)
0xbf3c2  stloc.s  6
0xbf3c4  ldarg.s  5
0xbf3c6  brfalse.s loc_BF3E3
0xbf3c8  ldloc.s  6
0xbf3ca  ldfld    valuetype Microsoft.ReportingServices.ReportIntermediateFormat.ValueType StyleInformationAttribute::ValueType
0xbf3cf  brtrue.s loc_BF3E3
0xbf3d1  ldloc.s  6
0xbf3d3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo StyleInformationAttribute::Value
0xbf3d8  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_MeDotValueDetected()
0xbf3dd  brfalse.s loc_BF3E3
0xbf3df  ldarg.s  6
0xbf3e1  ldc.i4.1
0xbf3e2  stind.i1
0xbf3e3  ldarg.0
0xbf3e4  ldloc.s  5
0xbf3e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute>::get_Item(!!T0)
0xbf3eb  ldfld    string StyleInformationAttribute::Name
0xbf3f0  stloc.s  8
0xbf3f2  ldloc.s  8
0xbf3f4  brfalse  loc_C0082
0xbf3f9  ldloc.s  8
0xbf3fb  call     instance int32 [mscorlib]System.String::get_Length()
0xbf400  stloc.s  9
0xbf402  ldloc.s  9
0xbf404  ldc.i4.5
0xbf405  sub
0xbf406  switch   loc_BFB01, loc_BFAEB, loc_C0082, loc_BF67C, loc_BF617, loc_BF641, loc_BF50F, loc_BF4E2, loc_BF4B8, loc_BF5A6, loc_BF55F, loc_BF468, loc_BF5ED, loc_C0082, loc_BFB17, loc_BF6D0, loc_BF6BA, loc_BF9CD, loc_BF6E6, loc_C0082, loc_C0082, loc_BF9B7
0xbf463  br       loc_C0082
0xbf468  ldloc.s  8
0xbf46a  ldc.i4.6
0xbf46b  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf470  stloc.s  0xA
0xbf472  ldloc.s  0xA
0xbf474  ldc.i4.s 0x57
0xbf476  bgt.un.s loc_BF498
0xbf478  ldloc.s  0xA
0xbf47a  ldc.i4.s 0x43
0xbf47c  beq      loc_BF728
0xbf481  ldloc.s  0xA
0xbf483  ldc.i4.s 0x53
0xbf485  beq      loc_BF73E
0xbf48a  ldloc.s  0xA
0xbf48c  ldc.i4.s 0x57
0xbf48e  beq      loc_BF754
0xbf493  br       loc_C0082
0xbf498  ldloc.s  0xA
0xbf49a  ldc.i4.s 0x61
0xbf49c  beq      loc_BF712
0xbf4a1  ldloc.s  0xA
0xbf4a3  ldc.i4.s 0x63
0xbf4a5  beq      loc_BF76A
0xbf4aa  ldloc.s  0xA
0xbf4ac  ldc.i4.s 0x6F
0xbf4ae  beq      loc_BF6FC
0xbf4b3  br       loc_C0082
0xbf4b8  ldloc.s  8
0xbf4ba  ldc.i4.0
0xbf4bb  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf4c0  stloc.s  0xA
0xbf4c2  ldloc.s  0xA
0xbf4c4  ldc.i4.s 0x45
0xbf4c6  beq      loc_BF780
0xbf4cb  ldloc.s  0xA
0xbf4cd  ldc.i4.s 0x50
0xbf4cf  beq      loc_BF7AC
0xbf4d4  ldloc.s  0xA
0xbf4d6  ldc.i4.s 0x56
0xbf4d8  beq      loc_BF796
0xbf4dd  br       loc_C0082
0xbf4e2  ldloc.s  8
0xbf4e4  ldc.i4.0
0xbf4e5  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf4ea  stloc.s  0xA
0xbf4ec  ldloc.s  0xA
0xbf4ee  ldc.i4.s 0x50
0xbf4f0  sub
0xbf4f1  switch   loc_BF7D8, loc_C0082, loc_C0082, loc_BF7EE, loc_BF7C2
0xbf50a  br       loc_C0082
0xbf50f  ldloc.s  8
0xbf511  ldc.i4.7
0xbf512  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf517  stloc.s  0xA
0xbf519  ldloc.s  0xA
0xbf51b  ldc.i4.s 0x4D
0xbf51d  bgt.un.s loc_BF53F
0xbf51f  ldloc.s  0xA
0xbf521  ldc.i4.s 0x42
0xbf523  beq      loc_BF883
0xbf528  ldloc.s  0xA
0xbf52a  ldc.i4.s 0x4C
0xbf52c  beq      loc_BF857
0xbf531  ldloc.s  0xA
0xbf533  ldc.i4.s 0x4D
0xbf535  beq      loc_BF86D
0xbf53a  br       loc_C0082
0xbf53f  ldloc.s  0xA
0xbf541  ldc.i4.s 0x69
0xbf543  beq      loc_BF841
0xbf548  ldloc.s  0xA
0xbf54a  ldc.i4.s 0x6F
0xbf54c  beq      loc_BF804
0xbf551  ldloc.s  0xA
0xbf553  ldc.i4.s 0x74
0xbf555  beq      loc_BF82B
0xbf55a  br       loc_C0082
0xbf55f  ldloc.s  8
0xbf561  ldc.i4.6
0xbf562  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf567  stloc.s  0xA
0xbf569  ldloc.s  0xA
0xbf56b  ldc.i4.s 0x53
0xbf56d  bgt.un.s loc_BF586
0xbf56f  ldloc.s  0xA
0xbf571  ldc.i4.s 0x43
0xbf573  beq      loc_BF899
0xbf578  ldloc.s  0xA
0xbf57a  ldc.i4.s 0x53
0xbf57c  beq      loc_BF8AF
0xbf581  br       loc_C0082
0xbf586  ldloc.s  0xA
0xbf588  ldc.i4.s 0x57
0xbf58a  beq      loc_BF8C5
0xbf58f  ldloc.s  0xA
0xbf591  ldc.i4.s 0x6C
0xbf593  beq      loc_BF8F1
0xbf598  ldloc.s  0xA
0xbf59a  ldc.i4.s 0x6F
0xbf59c  beq      loc_BF8DB
0xbf5a1  br       loc_C0082
0xbf5a6  ldloc.s  8
0xbf5a8  ldc.i4.6
0xbf5a9  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf5ae  stloc.s  0xA
0xbf5b0  ldloc.s  0xA
0xbf5b2  ldc.i4.s 0x53
0xbf5b4  bgt.un.s loc_BF5CD
0xbf5b6  ldloc.s  0xA
0xbf5b8  ldc.i4.s 0x43
0xbf5ba  beq      loc_BF907
0xbf5bf  ldloc.s  0xA
0xbf5c1  ldc.i4.s 0x53
0xbf5c3  beq      loc_BF91D
0xbf5c8  br       loc_C0082
0xbf5cd  ldloc.s  0xA
0xbf5cf  ldc.i4.s 0x57
0xbf5d1  beq      loc_BF933
0xbf5d6  ldloc.s  0xA
0xbf5d8  ldc.i4.s 0x63
0xbf5da  beq      loc_BF949
0xbf5df  ldloc.s  0xA
0xbf5e1  ldc.i4.s 0x6C
0xbf5e3  beq      loc_BF95F
0xbf5e8  br       loc_C0082
0xbf5ed  ldloc.s  8
0xbf5ef  ldc.i4.6
0xbf5f0  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf5f5  stloc.s  0xA
0xbf5f7  ldloc.s  0xA
0xbf5f9  ldc.i4.s 0x43
0xbf5fb  beq      loc_BF975
0xbf600  ldloc.s  0xA
0xbf602  ldc.i4.s 0x53
0xbf604  beq      loc_BF98B
0xbf609  ldloc.s  0xA
0xbf60b  ldc.i4.s 0x57
0xbf60d  beq      loc_BF9A1
0xbf612  br       loc_C0082
0xbf617  ldloc.s  8
0xbf619  ldc.i4.0
0xbf61a  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf61f  stloc.s  0xA
0xbf621  ldloc.s  0xA
0xbf623  ldc.i4.s 0x44
0xbf625  beq      loc_BFA0F
0xbf62a  ldloc.s  0xA
0xbf62c  ldc.i4.s 0x46
0xbf62e  beq      loc_BF9E3
0xbf633  ldloc.s  0xA
0xbf635  ldc.i4.s 0x54
0xbf637  beq      loc_BF9F9
0xbf63c  br       loc_C0082
0xbf641  ldloc.s  8
0xbf643  ldc.i4.4
0xbf644  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf649  stloc.s  0xA
0xbf64b  ldloc.s  0xA
0xbf64d  ldc.i4.s 0x45
0xbf64f  sub
0xbf650  switch   loc_BFA7D, loc_BFA25, loc_C0082, loc_BFA67
0xbf665  ldloc.s  0xA
0xbf667  ldc.i4.s 0x57
0xbf669  beq      loc_BFA3B
0xbf66e  ldloc.s  0xA
0xbf670  ldc.i4.s 0x69
0xbf672  beq      loc_BFA51
0xbf677  br       loc_C0082
0xbf67c  ldloc.s  8
0xbf67e  ldc.i4.0
0xbf67f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbf684  stloc.s  0xA
0xbf686  ldloc.s  0xA
0xbf688  ldc.i4.s 0x46
0xbf68a  bgt.un.s loc_BF6A3
0xbf68c  ldloc.s  0xA
0xbf68e  ldc.i4.s 0x43
0xbf690  beq      loc_BFABF
0xbf695  ldloc.s  0xA
0xbf697  ldc.i4.s 0x46
0xbf699  beq      loc_BFA93
0xbf69e  br       loc_C0082
0xbf6a3  ldloc.s  0xA
0xbf6a5  ldc.i4.s 0x4C
0xbf6a7  beq      loc_BFAA9
0xbf6ac  ldloc.s  0xA
0xbf6ae  ldc.i4.s 0x50
0xbf6b0  beq      loc_BFAD5
0xbf6b5  br       loc_C0082
0xbf6ba  ldloc.s  8
0xbf6bc  ldstr    aBackgroundimag_2// "BackgroundImageSource"
0xbf6c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf6c6  brtrue   loc_BFB2D
0xbf6cb  br       loc_C0082
0xbf6d0  ldloc.s  8
0xbf6d2  ldstr    aBackgroundimag// "BackgroundImageValue"
0xbf6d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf6dc  brtrue   loc_BFB3A
0xbf6e1  br       loc_C0082
0xbf6e6  ldloc.s  8
0xbf6e8  ldstr    aBackgroundimag_0// "BackgroundImageMIMEType"
0xbf6ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf6f2  brtrue   loc_BFB47
0xbf6f7  br       loc_C0082
0xbf6fc  ldloc.s  8
0xbf6fe  ldstr    aBackgroundrepe// "BackgroundRepeat"
0xbf703  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf708  brtrue   loc_BFB54
0xbf70d  br       loc_C0082
0xbf712  ldloc.s  8
0xbf714  ldstr    aTransparentcol// "TransparentColor"
0xbf719  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf71e  brtrue   loc_BFBB2
0xbf723  br       loc_C0082
0xbf728  ldloc.s  8
0xbf72a  ldstr    aBordercolorrig// "BorderColorRight"
0xbf72f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf734  brtrue   loc_BFBD9
0xbf739  br       loc_C0082
0xbf73e  ldloc.s  8
0xbf740  ldstr    aBorderstylerig// "BorderStyleRight"
0xbf745  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf74a  brtrue   loc_BFC29
0xbf74f  br       loc_C0082
0xbf754  ldloc.s  8
0xbf756  ldstr    aBorderwidthrig// "BorderWidthRight"
0xbf75b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf760  brtrue   loc_BFC52
0xbf765  br       loc_C0082
0xbf76a  ldloc.s  8
0xbf76c  ldstr    aCurrencylangua// "CurrencyLanguage"
0xbf771  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf776  brtrue   loc_BFF4A
0xbf77b  br       loc_C0082
0xbf780  ldloc.s  8
0xbf782  ldstr    aEmbeddingmode// "EmbeddingMode"
0xbf787  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf78c  brtrue   loc_BFB7D
0xbf791  br       loc_C0082
0xbf796  ldloc.s  8
0xbf798  ldstr    aVerticalalign// "VerticalAlign"
0xbf79d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf7a2  brtrue   loc_BFDC8
0xbf7a7  br       loc_C0082
0xbf7ac  ldloc.s  8
0xbf7ae  ldstr    aPaddingbottom// "PaddingBottom"
0xbf7b3  call     bool [mscorlib]System.String::op_Equality(string, string)
  ... truncated ...
```
