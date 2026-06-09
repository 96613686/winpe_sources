# Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateAndCreateStyle

- ea: `0x1cbc90`
- end: `0x1cc89c`
- name: `Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateAndCreateStyle`
- size: `3084`
- prototype: ``
- caller_count: `25`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b6fe0`
- `0x1b7df0`
- `0x1b84d0`
- `0x1b91d0`
- `0x1b9640`
- `0x1b9c30`
- `0x1ba120`
- `0x1baac0`
- `0x1bb230`
- `0x1bb800`
- `0x1bbdc0`
- `0x1bc6b0`
- `0x1bd9a0`
- `0x1bde50`
- `0x1bf310`
- `0x1bf4b0`
- `0x1bf970`
- `0x1bfab0`
- `0x1bfdb0`
- `0x1c0040`
- `0x1c0240`
- `0x1c0490`
- `0x1c0840`
- `0x1c1b50`
- `0x1c2960`

## callees

- `0x18ecb0`
- `0x18f0d0`
- `0x196a20`
- `0x196a40`
- `0x196ab0`
- `0x1cb3b0`
- `0x1cb450`
- `0x1cb690`
- `0x1cb6e0`
- `0x1cb750`
- `0x1cb820`
- `0x1cb880`
- `0x1cb8d0`
- `0x1cb920`
- `0x1cb970`
- `0x1cb9c0`
- `0x1cba10`
- `0x1cba60`
- `0x1cbab0`
- `0x1cbb00`
- `0x1cbb50`
- `0x1cbba0`
- `0x1cbbf0`
- `0x1cbc90`

## pseudocode

```c

```

## disassembly

```asm
0x1cbc90  ldc.i4.0
0x1cbc91  newobj   instance void Microsoft.ReportingServices.ReportProcessing.Style::.ctor(valuetype Microsoft.ReportingServices.ReportProcessing.ConstructionPhase phase)
0x1cbc96  stloc.0
0x1cbc97  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1cbc9c  ldarg.0
0x1cbc9d  ldnull
0x1cbc9e  cgt.un
0x1cbca0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x1cbca5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1cbcaa  ldarg.1
0x1cbcab  ldnull
0x1cbcac  cgt.un
0x1cbcae  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x1cbcb3  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1cbcb8  ldarg.0
0x1cbcb9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1cbcbe  ldarg.1
0x1cbcbf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1cbcc4  ceq
0x1cbcc6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x1cbccb  ldnull
0x1cbccc  stloc.1
0x1cbccd  ldnull
0x1cbcce  stloc.2
0x1cbccf  ldnull
0x1cbcd0  stloc.3
0x1cbcd1  ldc.i4.0
0x1cbcd2  stloc.s  4
0x1cbcd4  br       loc_1CC870
0x1cbcd9  ldarg.0
0x1cbcda  ldloc.s  4
0x1cbcdc  callvirt instance string Microsoft.ReportingServices.ReportProcessing.StringList::get_Item(int32 index)
0x1cbce1  stloc.s  6
0x1cbce3  ldloc.s  6
0x1cbce5  brfalse  loc_1CC85F
0x1cbcea  ldloc.s  6
0x1cbcec  call     instance int32 [mscorlib]System.String::get_Length()
0x1cbcf1  stloc.s  7
0x1cbcf3  ldloc.s  7
0x1cbcf5  ldc.i4.5
0x1cbcf6  sub
0x1cbcf7  switch   loc_1CC2D8, loc_1CC296, loc_1CC85F, loc_1CBF07, loc_1CBE9F, loc_1CBEC9, loc_1CBD97, loc_1CC2EE, loc_1CBF31, loc_1CBE2E, loc_1CBDE7, loc_1CBD59, loc_1CBE75, loc_1CC85F, loc_1CC85F, loc_1CBF68, loc_1CBF52, loc_1CC1A4, loc_1CBF7E, loc_1CC85F, loc_1CC85F, loc_1CC18E
0x1cbd54  br       loc_1CC85F
0x1cbd59  ldloc.s  6
0x1cbd5b  ldc.i4.6
0x1cbd5c  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbd61  stloc.s  8
0x1cbd63  ldloc.s  8
0x1cbd65  ldc.i4.s 0x53
0x1cbd67  bgt.un.s loc_1CBD80
0x1cbd69  ldloc.s  8
0x1cbd6b  ldc.i4.s 0x43
0x1cbd6d  beq      loc_1CBFAA
0x1cbd72  ldloc.s  8
0x1cbd74  ldc.i4.s 0x53
0x1cbd76  beq      loc_1CBFC0
0x1cbd7b  br       loc_1CC85F
0x1cbd80  ldloc.s  8
0x1cbd82  ldc.i4.s 0x57
0x1cbd84  beq      loc_1CBFD6
0x1cbd89  ldloc.s  8
0x1cbd8b  ldc.i4.s 0x6F
0x1cbd8d  beq      loc_1CBF94
0x1cbd92  br       loc_1CC85F
0x1cbd97  ldloc.s  6
0x1cbd99  ldc.i4.7
0x1cbd9a  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbd9f  stloc.s  8
0x1cbda1  ldloc.s  8
0x1cbda3  ldc.i4.s 0x4D
0x1cbda5  bgt.un.s loc_1CBDC7
0x1cbda7  ldloc.s  8
0x1cbda9  ldc.i4.s 0x42
0x1cbdab  beq      loc_1CC05A
0x1cbdb0  ldloc.s  8
0x1cbdb2  ldc.i4.s 0x4C
0x1cbdb4  beq      loc_1CC02E
0x1cbdb9  ldloc.s  8
0x1cbdbb  ldc.i4.s 0x4D
0x1cbdbd  beq      loc_1CC044
0x1cbdc2  br       loc_1CC85F
0x1cbdc7  ldloc.s  8
0x1cbdc9  ldc.i4.s 0x69
0x1cbdcb  beq      loc_1CC018
0x1cbdd0  ldloc.s  8
0x1cbdd2  ldc.i4.s 0x6F
0x1cbdd4  beq      loc_1CBFEC
0x1cbdd9  ldloc.s  8
0x1cbddb  ldc.i4.s 0x74
0x1cbddd  beq      loc_1CC002
0x1cbde2  br       loc_1CC85F
0x1cbde7  ldloc.s  6
0x1cbde9  ldc.i4.6
0x1cbdea  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbdef  stloc.s  8
0x1cbdf1  ldloc.s  8
0x1cbdf3  ldc.i4.s 0x53
0x1cbdf5  bgt.un.s loc_1CBE0E
0x1cbdf7  ldloc.s  8
0x1cbdf9  ldc.i4.s 0x43
0x1cbdfb  beq      loc_1CC070
0x1cbe00  ldloc.s  8
0x1cbe02  ldc.i4.s 0x53
0x1cbe04  beq      loc_1CC086
0x1cbe09  br       loc_1CC85F
0x1cbe0e  ldloc.s  8
0x1cbe10  ldc.i4.s 0x57
0x1cbe12  beq      loc_1CC09C
0x1cbe17  ldloc.s  8
0x1cbe19  ldc.i4.s 0x6C
0x1cbe1b  beq      loc_1CC0C8
0x1cbe20  ldloc.s  8
0x1cbe22  ldc.i4.s 0x6F
0x1cbe24  beq      loc_1CC0B2
0x1cbe29  br       loc_1CC85F
0x1cbe2e  ldloc.s  6
0x1cbe30  ldc.i4.6
0x1cbe31  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbe36  stloc.s  8
0x1cbe38  ldloc.s  8
0x1cbe3a  ldc.i4.s 0x53
0x1cbe3c  bgt.un.s loc_1CBE55
0x1cbe3e  ldloc.s  8
0x1cbe40  ldc.i4.s 0x43
0x1cbe42  beq      loc_1CC0DE
0x1cbe47  ldloc.s  8
0x1cbe49  ldc.i4.s 0x53
0x1cbe4b  beq      loc_1CC0F4
0x1cbe50  br       loc_1CC85F
0x1cbe55  ldloc.s  8
0x1cbe57  ldc.i4.s 0x57
0x1cbe59  beq      loc_1CC10A
0x1cbe5e  ldloc.s  8
0x1cbe60  ldc.i4.s 0x63
0x1cbe62  beq      loc_1CC120
0x1cbe67  ldloc.s  8
0x1cbe69  ldc.i4.s 0x6C
0x1cbe6b  beq      loc_1CC136
0x1cbe70  br       loc_1CC85F
0x1cbe75  ldloc.s  6
0x1cbe77  ldc.i4.6
0x1cbe78  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbe7d  stloc.s  8
0x1cbe7f  ldloc.s  8
0x1cbe81  ldc.i4.s 0x43
0x1cbe83  beq      loc_1CC14C
0x1cbe88  ldloc.s  8
0x1cbe8a  ldc.i4.s 0x53
0x1cbe8c  beq      loc_1CC162
0x1cbe91  ldloc.s  8
0x1cbe93  ldc.i4.s 0x57
0x1cbe95  beq      loc_1CC178
0x1cbe9a  br       loc_1CC85F
0x1cbe9f  ldloc.s  6
0x1cbea1  ldc.i4.0
0x1cbea2  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbea7  stloc.s  8
0x1cbea9  ldloc.s  8
0x1cbeab  ldc.i4.s 0x44
0x1cbead  beq      loc_1CC1E6
0x1cbeb2  ldloc.s  8
0x1cbeb4  ldc.i4.s 0x46
0x1cbeb6  beq      loc_1CC1BA
0x1cbebb  ldloc.s  8
0x1cbebd  ldc.i4.s 0x54
0x1cbebf  beq      loc_1CC1D0
0x1cbec4  br       loc_1CC85F
0x1cbec9  ldloc.s  6
0x1cbecb  ldc.i4.4
0x1cbecc  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbed1  stloc.s  8
0x1cbed3  ldloc.s  8
0x1cbed5  ldc.i4.s 0x48
0x1cbed7  bgt.un.s loc_1CBEF0
0x1cbed9  ldloc.s  8
0x1cbedb  ldc.i4.s 0x46
0x1cbedd  beq      loc_1CC1FC
0x1cbee2  ldloc.s  8
0x1cbee4  ldc.i4.s 0x48
0x1cbee6  beq      loc_1CC23E
0x1cbeeb  br       loc_1CC85F
0x1cbef0  ldloc.s  8
0x1cbef2  ldc.i4.s 0x57
0x1cbef4  beq      loc_1CC212
0x1cbef9  ldloc.s  8
0x1cbefb  ldc.i4.s 0x69
0x1cbefd  beq      loc_1CC228
0x1cbf02  br       loc_1CC85F
0x1cbf07  ldloc.s  6
0x1cbf09  ldc.i4.0
0x1cbf0a  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbf0f  stloc.s  8
0x1cbf11  ldloc.s  8
0x1cbf13  ldc.i4.s 0x43
0x1cbf15  beq      loc_1CC280
0x1cbf1a  ldloc.s  8
0x1cbf1c  ldc.i4.s 0x46
0x1cbf1e  beq      loc_1CC254
0x1cbf23  ldloc.s  8
0x1cbf25  ldc.i4.s 0x4C
0x1cbf27  beq      loc_1CC26A
0x1cbf2c  br       loc_1CC85F
0x1cbf31  ldloc.s  6
0x1cbf33  ldc.i4.0
0x1cbf34  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1cbf39  stloc.s  8
0x1cbf3b  ldloc.s  8
0x1cbf3d  ldc.i4.s 0x50
0x1cbf3f  beq      loc_1CC2C2
0x1cbf44  ldloc.s  8
0x1cbf46  ldc.i4.s 0x56
0x1cbf48  beq      loc_1CC2AC
0x1cbf4d  br       loc_1CC85F
0x1cbf52  ldloc.s  6
0x1cbf54  ldstr    aBackgroundimag_2// "BackgroundImageSource"
0x1cbf59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbf5e  brtrue   loc_1CC304
0x1cbf63  br       loc_1CC85F
0x1cbf68  ldloc.s  6
0x1cbf6a  ldstr    aBackgroundimag// "BackgroundImageValue"
0x1cbf6f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbf74  brtrue   loc_1CC312
0x1cbf79  br       loc_1CC85F
0x1cbf7e  ldloc.s  6
0x1cbf80  ldstr    aBackgroundimag_0// "BackgroundImageMIMEType"
0x1cbf85  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbf8a  brtrue   loc_1CC320
0x1cbf8f  br       loc_1CC85F
0x1cbf94  ldloc.s  6
0x1cbf96  ldstr    aBackgroundrepe// "BackgroundRepeat"
0x1cbf9b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbfa0  brtrue   loc_1CC32E
0x1cbfa5  br       loc_1CC85F
0x1cbfaa  ldloc.s  6
0x1cbfac  ldstr    aBordercolorrig// "BorderColorRight"
0x1cbfb1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbfb6  brtrue   loc_1CC367
0x1cbfbb  br       loc_1CC85F
0x1cbfc0  ldloc.s  6
0x1cbfc2  ldstr    aBorderstylerig// "BorderStyleRight"
0x1cbfc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbfcc  brtrue   loc_1CC39D
0x1cbfd1  br       loc_1CC85F
0x1cbfd6  ldloc.s  6
0x1cbfd8  ldstr    aBorderwidthrig// "BorderWidthRight"
0x1cbfdd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbfe2  brtrue   loc_1CC3D3
0x1cbfe7  br       loc_1CC85F
0x1cbfec  ldloc.s  6
0x1cbfee  ldstr    aBordercolor// "BorderColor"
0x1cbff3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cbff8  brtrue   loc_1CC367
0x1cbffd  br       loc_1CC85F
0x1cc002  ldloc.s  6
0x1cc004  ldstr    aBorderstyle// "BorderStyle"
0x1cc009  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc00e  brtrue   loc_1CC39D
0x1cc013  br       loc_1CC85F
0x1cc018  ldloc.s  6
0x1cc01a  ldstr    aBorderwidth// "BorderWidth"
0x1cc01f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc024  brtrue   loc_1CC3D3
0x1cc029  br       loc_1CC85F
0x1cc02e  ldloc.s  6
0x1cc030  ldstr    aPaddingleft// "PaddingLeft"
0x1cc035  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc03a  brtrue   loc_1CC657
0x1cc03f  br       loc_1CC85F
0x1cc044  ldloc.s  6
0x1cc046  ldstr    aWritingmode// "WritingMode"
0x1cc04b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc050  brtrue   loc_1CC716
0x1cc055  br       loc_1CC85F
0x1cc05a  ldloc.s  6
0x1cc05c  ldstr    aUnicodebidi// "UnicodeBiDi"
0x1cc061  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc066  brtrue   loc_1CC78A
0x1cc06b  br       loc_1CC85F
0x1cc070  ldloc.s  6
0x1cc072  ldstr    aBordercolorlef// "BorderColorLeft"
0x1cc077  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc07c  brtrue   loc_1CC367
0x1cc081  br       loc_1CC85F
0x1cc086  ldloc.s  6
0x1cc088  ldstr    aBorderstylelef// "BorderStyleLeft"
0x1cc08d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc092  brtrue   loc_1CC39D
0x1cc097  br       loc_1CC85F
0x1cc09c  ldloc.s  6
0x1cc09e  ldstr    aBorderwidthlef// "BorderWidthLeft"
0x1cc0a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc0a8  brtrue   loc_1CC3D3
0x1cc0ad  br       loc_1CC85F
0x1cc0b2  ldloc.s  6
0x1cc0b4  ldstr    aBackgroundcolo// "BackgroundColor"
0x1cc0b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cc0be  brtrue   loc_1CC416
0x1cc0c3  br       loc_1CC85F
0x1cc0c8  ldloc.s  6
0x1cc0ca  ldstr    aNumerallanguag// "NumeralLanguage"
  ... truncated ...
```
