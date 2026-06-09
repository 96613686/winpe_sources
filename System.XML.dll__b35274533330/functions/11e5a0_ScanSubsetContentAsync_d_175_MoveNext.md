# <ScanSubsetContentAsync>d__175::MoveNext

- ea: `0x11e5a0`
- end: `0x11ebba`
- name: `<ScanSubsetContentAsync>d__175::MoveNext`
- size: `1562`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15dc0`
- `0x60de0`
- `0x61d30`
- `0x11e5a0`

## string_xrefs

- `0x11e6d4`: `Xml_ExpectDtdMarkup`
- `0x11e77f`: `Xml_ExpectDtdMarkup`
- `0x11e7c1`: `Xml_ExpectDtdMarkup`
- `0x11e860`: `Xml_ExpectDtdMarkup`
- `0x11e931`: `Xml_ExpectDtdMarkup`
- `0x11e9c2`: `Xml_ExpectDtdMarkup`
- `0x11e9ed`: `Xml_ExpectDtdMarkup`
- `0x11ea2c`: `Xml_ExpectDtdMarkup`
- `0x11eafe`: `Xml_ExpectDtdMarkup`
- `0x11eb7d`: `Xml_IncompleteDtdContent`

## pseudocode

```c

```

## disassembly

```asm
0x11e5a0  ldarg.0
0x11e5a1  ldfld    int32 <ScanSubsetContentAsync>d__175::<>1__state
0x11e5a6  stloc.0
0x11e5a7  ldarg.0
0x11e5a8  ldfld    class System.Xml.DtdParser <ScanSubsetContentAsync>d__175::<>4__this
0x11e5ad  stloc.1
0x11e5ae  ldloc.0
0x11e5af  brfalse  loc_11EB49
0x11e5b4  ldloc.1
0x11e5b5  ldfld    char[] System.Xml.DtdParser::chars
0x11e5ba  ldloc.1
0x11e5bb  ldfld    int32 System.Xml.DtdParser::curPos
0x11e5c0  ldelem.u2
0x11e5c1  stloc.3
0x11e5c2  ldloc.3
0x11e5c3  ldc.i4.s 0x3C
0x11e5c5  beq.s    loc_11E5D4
0x11e5c7  ldloc.3
0x11e5c8  ldc.i4.s 0x5D
0x11e5ca  beq      loc_11EA3E
0x11e5cf  br       loc_11EAE8
0x11e5d4  ldloc.1
0x11e5d5  ldfld    char[] System.Xml.DtdParser::chars
0x11e5da  ldloc.1
0x11e5db  ldfld    int32 System.Xml.DtdParser::curPos
0x11e5e0  ldc.i4.1
0x11e5e1  add
0x11e5e2  ldelem.u2
0x11e5e3  stloc.s  4
0x11e5e5  ldloc.s  4
0x11e5e7  ldc.i4.s 0x21
0x11e5e9  beq.s    loc_11E5F9
0x11e5eb  ldloc.s  4
0x11e5ed  ldc.i4.s 0x3F
0x11e5ef  beq      loc_11E9FC
0x11e5f4  br       loc_11EA12
0x11e5f9  ldloc.1
0x11e5fa  ldfld    char[] System.Xml.DtdParser::chars
0x11e5ff  ldloc.1
0x11e600  ldfld    int32 System.Xml.DtdParser::curPos
0x11e605  ldc.i4.2
0x11e606  add
0x11e607  ldelem.u2
0x11e608  stloc.s  5
0x11e60a  ldloc.s  5
0x11e60c  ldc.i4.s 0x41
0x11e60e  bgt.un.s loc_11E627
0x11e610  ldloc.s  5
0x11e612  ldc.i4.s 0x2D
0x11e614  beq      loc_11E97F
0x11e619  ldloc.s  5
0x11e61b  ldc.i4.s 0x41
0x11e61d  beq      loc_11E7D3
0x11e622  br       loc_11E9D1
0x11e627  ldloc.s  5
0x11e629  ldc.i4.s 0x45
0x11e62b  beq.s    loc_11E644
0x11e62d  ldloc.s  5
0x11e62f  ldc.i4.s 0x4E
0x11e631  beq      loc_11E890
0x11e636  ldloc.s  5
0x11e638  ldc.i4.s 0x5B
0x11e63a  beq      loc_11E961
0x11e63f  br       loc_11E9D1
0x11e644  ldloc.1
0x11e645  ldfld    char[] System.Xml.DtdParser::chars
0x11e64a  ldloc.1
0x11e64b  ldfld    int32 System.Xml.DtdParser::curPos
0x11e650  ldc.i4.3
0x11e651  add
0x11e652  ldelem.u2
0x11e653  ldc.i4.s 0x4C
0x11e655  bne.un   loc_11E703
0x11e65a  ldloc.1
0x11e65b  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11e660  ldloc.1
0x11e661  ldfld    int32 System.Xml.DtdParser::curPos
0x11e666  sub
0x11e667  ldc.i4.s 9
0x11e669  blt      loc_11EB08
0x11e66e  ldloc.1
0x11e66f  ldfld    char[] System.Xml.DtdParser::chars
0x11e674  ldloc.1
0x11e675  ldfld    int32 System.Xml.DtdParser::curPos
0x11e67a  ldc.i4.4
0x11e67b  add
0x11e67c  ldelem.u2
0x11e67d  ldc.i4.s 0x45
0x11e67f  bne.un.s loc_11E6CD
0x11e681  ldloc.1
0x11e682  ldfld    char[] System.Xml.DtdParser::chars
0x11e687  ldloc.1
0x11e688  ldfld    int32 System.Xml.DtdParser::curPos
0x11e68d  ldc.i4.5
0x11e68e  add
0x11e68f  ldelem.u2
0x11e690  ldc.i4.s 0x4D
0x11e692  bne.un.s loc_11E6CD
0x11e694  ldloc.1
0x11e695  ldfld    char[] System.Xml.DtdParser::chars
0x11e69a  ldloc.1
0x11e69b  ldfld    int32 System.Xml.DtdParser::curPos
0x11e6a0  ldc.i4.6
0x11e6a1  add
0x11e6a2  ldelem.u2
0x11e6a3  ldc.i4.s 0x45
0x11e6a5  bne.un.s loc_11E6CD
0x11e6a7  ldloc.1
0x11e6a8  ldfld    char[] System.Xml.DtdParser::chars
0x11e6ad  ldloc.1
0x11e6ae  ldfld    int32 System.Xml.DtdParser::curPos
0x11e6b3  ldc.i4.7
0x11e6b4  add
0x11e6b5  ldelem.u2
0x11e6b6  ldc.i4.s 0x4E
0x11e6b8  bne.un.s loc_11E6CD
0x11e6ba  ldloc.1
0x11e6bb  ldfld    char[] System.Xml.DtdParser::chars
0x11e6c0  ldloc.1
0x11e6c1  ldfld    int32 System.Xml.DtdParser::curPos
0x11e6c6  ldc.i4.8
0x11e6c7  add
0x11e6c8  ldelem.u2
0x11e6c9  ldc.i4.s 0x54
0x11e6cb  beq.s    loc_11E6DE
0x11e6cd  ldloc.1
0x11e6ce  ldloc.1
0x11e6cf  ldfld    int32 System.Xml.DtdParser::curPos
0x11e6d4  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x11e6d9  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11e6de  ldloc.1
0x11e6df  ldloc.1
0x11e6e0  ldfld    int32 System.Xml.DtdParser::curPos
0x11e6e5  ldc.i4.s 9
0x11e6e7  add
0x11e6e8  stfld    int32 System.Xml.DtdParser::curPos
0x11e6ed  ldloc.1
0x11e6ee  ldc.i4.2
0x11e6ef  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11e6f4  ldloc.1
0x11e6f5  ldc.i4.6
0x11e6f6  stfld    valuetype ScanningFunction System.Xml.DtdParser::nextScaningFunction
0x11e6fb  ldc.i4.s 0xC
0x11e6fd  stloc.2
0x11e6fe  leave    loc_11EBA5
0x11e703  ldloc.1
0x11e704  ldfld    char[] System.Xml.DtdParser::chars
0x11e709  ldloc.1
0x11e70a  ldfld    int32 System.Xml.DtdParser::curPos
0x11e70f  ldc.i4.3
0x11e710  add
0x11e711  ldelem.u2
0x11e712  ldc.i4.s 0x4E
0x11e714  bne.un   loc_11E7A7
0x11e719  ldloc.1
0x11e71a  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11e71f  ldloc.1
0x11e720  ldfld    int32 System.Xml.DtdParser::curPos
0x11e725  sub
0x11e726  ldc.i4.8
0x11e727  blt      loc_11EB08
0x11e72c  ldloc.1
0x11e72d  ldfld    char[] System.Xml.DtdParser::chars
0x11e732  ldloc.1
0x11e733  ldfld    int32 System.Xml.DtdParser::curPos
0x11e738  ldc.i4.4
0x11e739  add
0x11e73a  ldelem.u2
0x11e73b  ldc.i4.s 0x54
0x11e73d  bne.un.s loc_11E778
0x11e73f  ldloc.1
0x11e740  ldfld    char[] System.Xml.DtdParser::chars
0x11e745  ldloc.1
0x11e746  ldfld    int32 System.Xml.DtdParser::curPos
0x11e74b  ldc.i4.5
0x11e74c  add
0x11e74d  ldelem.u2
0x11e74e  ldc.i4.s 0x49
0x11e750  bne.un.s loc_11E778
0x11e752  ldloc.1
0x11e753  ldfld    char[] System.Xml.DtdParser::chars
0x11e758  ldloc.1
0x11e759  ldfld    int32 System.Xml.DtdParser::curPos
0x11e75e  ldc.i4.6
0x11e75f  add
0x11e760  ldelem.u2
0x11e761  ldc.i4.s 0x54
0x11e763  bne.un.s loc_11E778
0x11e765  ldloc.1
0x11e766  ldfld    char[] System.Xml.DtdParser::chars
0x11e76b  ldloc.1
0x11e76c  ldfld    int32 System.Xml.DtdParser::curPos
0x11e771  ldc.i4.7
0x11e772  add
0x11e773  ldelem.u2
0x11e774  ldc.i4.s 0x59
0x11e776  beq.s    loc_11E789
0x11e778  ldloc.1
0x11e779  ldloc.1
0x11e77a  ldfld    int32 System.Xml.DtdParser::curPos
0x11e77f  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x11e784  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11e789  ldloc.1
0x11e78a  ldloc.1
0x11e78b  ldfld    int32 System.Xml.DtdParser::curPos
0x11e790  ldc.i4.8
0x11e791  add
0x11e792  stfld    int32 System.Xml.DtdParser::curPos
0x11e797  ldloc.1
0x11e798  ldc.i4.s 0x14
0x11e79a  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11e79f  ldc.i4.s 0xD
0x11e7a1  stloc.2
0x11e7a2  leave    loc_11EBA5
0x11e7a7  ldloc.1
0x11e7a8  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11e7ad  ldloc.1
0x11e7ae  ldfld    int32 System.Xml.DtdParser::curPos
0x11e7b3  sub
0x11e7b4  ldc.i4.4
0x11e7b5  blt      loc_11EB08
0x11e7ba  ldloc.1
0x11e7bb  ldloc.1
0x11e7bc  ldfld    int32 System.Xml.DtdParser::curPos
0x11e7c1  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x11e7c6  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11e7cb  ldc.i4.s 9
0x11e7cd  stloc.2
0x11e7ce  leave    loc_11EBA5
0x11e7d3  ldloc.1
0x11e7d4  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11e7d9  ldloc.1
0x11e7da  ldfld    int32 System.Xml.DtdParser::curPos
0x11e7df  sub
0x11e7e0  ldc.i4.s 9
0x11e7e2  blt      loc_11EB08
0x11e7e7  ldloc.1
0x11e7e8  ldfld    char[] System.Xml.DtdParser::chars
0x11e7ed  ldloc.1
0x11e7ee  ldfld    int32 System.Xml.DtdParser::curPos
0x11e7f3  ldc.i4.3
0x11e7f4  add
0x11e7f5  ldelem.u2
0x11e7f6  ldc.i4.s 0x54
0x11e7f8  bne.un.s loc_11E859
0x11e7fa  ldloc.1
0x11e7fb  ldfld    char[] System.Xml.DtdParser::chars
0x11e800  ldloc.1
0x11e801  ldfld    int32 System.Xml.DtdParser::curPos
0x11e806  ldc.i4.4
0x11e807  add
0x11e808  ldelem.u2
0x11e809  ldc.i4.s 0x54
0x11e80b  bne.un.s loc_11E859
0x11e80d  ldloc.1
0x11e80e  ldfld    char[] System.Xml.DtdParser::chars
0x11e813  ldloc.1
0x11e814  ldfld    int32 System.Xml.DtdParser::curPos
0x11e819  ldc.i4.5
0x11e81a  add
0x11e81b  ldelem.u2
0x11e81c  ldc.i4.s 0x4C
0x11e81e  bne.un.s loc_11E859
0x11e820  ldloc.1
0x11e821  ldfld    char[] System.Xml.DtdParser::chars
0x11e826  ldloc.1
0x11e827  ldfld    int32 System.Xml.DtdParser::curPos
0x11e82c  ldc.i4.6
0x11e82d  add
0x11e82e  ldelem.u2
0x11e82f  ldc.i4.s 0x49
0x11e831  bne.un.s loc_11E859
0x11e833  ldloc.1
0x11e834  ldfld    char[] System.Xml.DtdParser::chars
0x11e839  ldloc.1
0x11e83a  ldfld    int32 System.Xml.DtdParser::curPos
0x11e83f  ldc.i4.7
0x11e840  add
0x11e841  ldelem.u2
0x11e842  ldc.i4.s 0x53
0x11e844  bne.un.s loc_11E859
0x11e846  ldloc.1
0x11e847  ldfld    char[] System.Xml.DtdParser::chars
0x11e84c  ldloc.1
0x11e84d  ldfld    int32 System.Xml.DtdParser::curPos
0x11e852  ldc.i4.8
0x11e853  add
0x11e854  ldelem.u2
0x11e855  ldc.i4.s 0x54
0x11e857  beq.s    loc_11E86A
0x11e859  ldloc.1
0x11e85a  ldloc.1
0x11e85b  ldfld    int32 System.Xml.DtdParser::curPos
0x11e860  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x11e865  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11e86a  ldloc.1
0x11e86b  ldloc.1
0x11e86c  ldfld    int32 System.Xml.DtdParser::curPos
0x11e871  ldc.i4.s 9
0x11e873  add
  ... truncated ...
```
