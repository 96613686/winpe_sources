# System.Xml.DtdParser::ScanAttlist6

- ea: `0x5f1e0`
- end: `0x5f47c`
- name: `System.Xml.DtdParser::ScanAttlist6`
- size: `668`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5dc90`
- `0x5f1e0`

## callees

- `0x5f1e0`
- `0x5f4d0`
- `0x60940`
- `0x60de0`

## string_xrefs

- `0x5f46d`: `Xml_IncompleteDtdContent`
- `0x5f2ee`: `Xml_ExpectAttType`
- `0x5f39e`: `Xml_ExpectAttType`
- `0x5f414`: `Xml_ExpectAttType`
- `0x5f43e`: `Xml_ExpectAttType`
- `0x5f451`: `Xml_ExpectAttType`

## pseudocode

```c

```

## disassembly

```asm
0x5f1e0  ldarg.0
0x5f1e1  ldfld    char[] System.Xml.DtdParser::chars
0x5f1e6  ldarg.0
0x5f1e7  ldfld    int32 System.Xml.DtdParser::curPos
0x5f1ec  ldelem.u2
0x5f1ed  stloc.0
0x5f1ee  ldloc.0
0x5f1ef  ldc.i4.s 0x22
0x5f1f1  beq.s    loc_5F200
0x5f1f3  ldloc.0
0x5f1f4  ldc.i4.s 0x23
0x5f1f6  beq.s    loc_5F213
0x5f1f8  ldloc.0
0x5f1f9  ldc.i4.s 0x27
0x5f1fb  bne.un   loc_5F44A
0x5f200  ldarg.0
0x5f201  ldc.i4.0
0x5f202  call     instance valuetype Token System.Xml.DtdParser::ScanLiteral(valuetype LiteralType literalType)
0x5f207  pop
0x5f208  ldarg.0
0x5f209  ldc.i4.s 0xD
0x5f20b  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5f210  ldc.i4.s 0x23
0x5f212  ret
0x5f213  ldarg.0
0x5f214  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5f219  ldarg.0
0x5f21a  ldfld    int32 System.Xml.DtdParser::curPos
0x5f21f  sub
0x5f220  ldc.i4.6
0x5f221  blt      loc_5F45B
0x5f226  ldarg.0
0x5f227  ldfld    char[] System.Xml.DtdParser::chars
0x5f22c  ldarg.0
0x5f22d  ldfld    int32 System.Xml.DtdParser::curPos
0x5f232  ldc.i4.1
0x5f233  add
0x5f234  ldelem.u2
0x5f235  stloc.1
0x5f236  ldloc.1
0x5f237  ldc.i4.s 0x46
0x5f239  beq      loc_5F3C1
0x5f23e  ldloc.1
0x5f23f  ldc.i4.s 0x49
0x5f241  beq      loc_5F312
0x5f246  ldloc.1
0x5f247  ldc.i4.s 0x52
0x5f249  bne.un   loc_5F437
0x5f24e  ldarg.0
0x5f24f  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5f254  ldarg.0
0x5f255  ldfld    int32 System.Xml.DtdParser::curPos
0x5f25a  sub
0x5f25b  ldc.i4.s 9
0x5f25d  blt      loc_5F45B
0x5f262  ldarg.0
0x5f263  ldfld    char[] System.Xml.DtdParser::chars
0x5f268  ldarg.0
0x5f269  ldfld    int32 System.Xml.DtdParser::curPos
0x5f26e  ldc.i4.2
0x5f26f  add
0x5f270  ldelem.u2
0x5f271  ldc.i4.s 0x45
0x5f273  bne.un.s loc_5F2E7
0x5f275  ldarg.0
0x5f276  ldfld    char[] System.Xml.DtdParser::chars
0x5f27b  ldarg.0
0x5f27c  ldfld    int32 System.Xml.DtdParser::curPos
0x5f281  ldc.i4.3
0x5f282  add
0x5f283  ldelem.u2
0x5f284  ldc.i4.s 0x51
0x5f286  bne.un.s loc_5F2E7
0x5f288  ldarg.0
0x5f289  ldfld    char[] System.Xml.DtdParser::chars
0x5f28e  ldarg.0
0x5f28f  ldfld    int32 System.Xml.DtdParser::curPos
0x5f294  ldc.i4.4
0x5f295  add
0x5f296  ldelem.u2
0x5f297  ldc.i4.s 0x55
0x5f299  bne.un.s loc_5F2E7
0x5f29b  ldarg.0
0x5f29c  ldfld    char[] System.Xml.DtdParser::chars
0x5f2a1  ldarg.0
0x5f2a2  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2a7  ldc.i4.5
0x5f2a8  add
0x5f2a9  ldelem.u2
0x5f2aa  ldc.i4.s 0x49
0x5f2ac  bne.un.s loc_5F2E7
0x5f2ae  ldarg.0
0x5f2af  ldfld    char[] System.Xml.DtdParser::chars
0x5f2b4  ldarg.0
0x5f2b5  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2ba  ldc.i4.6
0x5f2bb  add
0x5f2bc  ldelem.u2
0x5f2bd  ldc.i4.s 0x52
0x5f2bf  bne.un.s loc_5F2E7
0x5f2c1  ldarg.0
0x5f2c2  ldfld    char[] System.Xml.DtdParser::chars
0x5f2c7  ldarg.0
0x5f2c8  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2cd  ldc.i4.7
0x5f2ce  add
0x5f2cf  ldelem.u2
0x5f2d0  ldc.i4.s 0x45
0x5f2d2  bne.un.s loc_5F2E7
0x5f2d4  ldarg.0
0x5f2d5  ldfld    char[] System.Xml.DtdParser::chars
0x5f2da  ldarg.0
0x5f2db  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2e0  ldc.i4.8
0x5f2e1  add
0x5f2e2  ldelem.u2
0x5f2e3  ldc.i4.s 0x44
0x5f2e5  beq.s    loc_5F2F8
0x5f2e7  ldarg.0
0x5f2e8  ldarg.0
0x5f2e9  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2ee  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x5f2f3  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f2f8  ldarg.0
0x5f2f9  ldarg.0
0x5f2fa  ldfld    int32 System.Xml.DtdParser::curPos
0x5f2ff  ldc.i4.s 9
0x5f301  add
0x5f302  stfld    int32 System.Xml.DtdParser::curPos
0x5f307  ldarg.0
0x5f308  ldc.i4.s 0xD
0x5f30a  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5f30f  ldc.i4.s 0x14
0x5f311  ret
0x5f312  ldarg.0
0x5f313  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5f318  ldarg.0
0x5f319  ldfld    int32 System.Xml.DtdParser::curPos
0x5f31e  sub
0x5f31f  ldc.i4.8
0x5f320  blt      loc_5F45B
0x5f325  ldarg.0
0x5f326  ldfld    char[] System.Xml.DtdParser::chars
0x5f32b  ldarg.0
0x5f32c  ldfld    int32 System.Xml.DtdParser::curPos
0x5f331  ldc.i4.2
0x5f332  add
0x5f333  ldelem.u2
0x5f334  ldc.i4.s 0x4D
0x5f336  bne.un.s loc_5F397
0x5f338  ldarg.0
0x5f339  ldfld    char[] System.Xml.DtdParser::chars
0x5f33e  ldarg.0
0x5f33f  ldfld    int32 System.Xml.DtdParser::curPos
0x5f344  ldc.i4.3
0x5f345  add
0x5f346  ldelem.u2
0x5f347  ldc.i4.s 0x50
0x5f349  bne.un.s loc_5F397
0x5f34b  ldarg.0
0x5f34c  ldfld    char[] System.Xml.DtdParser::chars
0x5f351  ldarg.0
0x5f352  ldfld    int32 System.Xml.DtdParser::curPos
0x5f357  ldc.i4.4
0x5f358  add
0x5f359  ldelem.u2
0x5f35a  ldc.i4.s 0x4C
0x5f35c  bne.un.s loc_5F397
0x5f35e  ldarg.0
0x5f35f  ldfld    char[] System.Xml.DtdParser::chars
0x5f364  ldarg.0
0x5f365  ldfld    int32 System.Xml.DtdParser::curPos
0x5f36a  ldc.i4.5
0x5f36b  add
0x5f36c  ldelem.u2
0x5f36d  ldc.i4.s 0x49
0x5f36f  bne.un.s loc_5F397
0x5f371  ldarg.0
0x5f372  ldfld    char[] System.Xml.DtdParser::chars
0x5f377  ldarg.0
0x5f378  ldfld    int32 System.Xml.DtdParser::curPos
0x5f37d  ldc.i4.6
0x5f37e  add
0x5f37f  ldelem.u2
0x5f380  ldc.i4.s 0x45
0x5f382  bne.un.s loc_5F397
0x5f384  ldarg.0
0x5f385  ldfld    char[] System.Xml.DtdParser::chars
0x5f38a  ldarg.0
0x5f38b  ldfld    int32 System.Xml.DtdParser::curPos
0x5f390  ldc.i4.7
0x5f391  add
0x5f392  ldelem.u2
0x5f393  ldc.i4.s 0x44
0x5f395  beq.s    loc_5F3A8
0x5f397  ldarg.0
0x5f398  ldarg.0
0x5f399  ldfld    int32 System.Xml.DtdParser::curPos
0x5f39e  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x5f3a3  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f3a8  ldarg.0
0x5f3a9  ldarg.0
0x5f3aa  ldfld    int32 System.Xml.DtdParser::curPos
0x5f3af  ldc.i4.8
0x5f3b0  add
0x5f3b1  stfld    int32 System.Xml.DtdParser::curPos
0x5f3b6  ldarg.0
0x5f3b7  ldc.i4.s 0xD
0x5f3b9  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5f3be  ldc.i4.s 0x15
0x5f3c0  ret
0x5f3c1  ldarg.0
0x5f3c2  ldfld    char[] System.Xml.DtdParser::chars
0x5f3c7  ldarg.0
0x5f3c8  ldfld    int32 System.Xml.DtdParser::curPos
0x5f3cd  ldc.i4.2
0x5f3ce  add
0x5f3cf  ldelem.u2
0x5f3d0  ldc.i4.s 0x49
0x5f3d2  bne.un.s loc_5F40D
0x5f3d4  ldarg.0
0x5f3d5  ldfld    char[] System.Xml.DtdParser::chars
0x5f3da  ldarg.0
0x5f3db  ldfld    int32 System.Xml.DtdParser::curPos
0x5f3e0  ldc.i4.3
0x5f3e1  add
0x5f3e2  ldelem.u2
0x5f3e3  ldc.i4.s 0x58
0x5f3e5  bne.un.s loc_5F40D
0x5f3e7  ldarg.0
0x5f3e8  ldfld    char[] System.Xml.DtdParser::chars
0x5f3ed  ldarg.0
0x5f3ee  ldfld    int32 System.Xml.DtdParser::curPos
0x5f3f3  ldc.i4.4
0x5f3f4  add
0x5f3f5  ldelem.u2
0x5f3f6  ldc.i4.s 0x45
0x5f3f8  bne.un.s loc_5F40D
0x5f3fa  ldarg.0
0x5f3fb  ldfld    char[] System.Xml.DtdParser::chars
0x5f400  ldarg.0
0x5f401  ldfld    int32 System.Xml.DtdParser::curPos
0x5f406  ldc.i4.5
0x5f407  add
0x5f408  ldelem.u2
0x5f409  ldc.i4.s 0x44
0x5f40b  beq.s    loc_5F41E
0x5f40d  ldarg.0
0x5f40e  ldarg.0
0x5f40f  ldfld    int32 System.Xml.DtdParser::curPos
0x5f414  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x5f419  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f41e  ldarg.0
0x5f41f  ldarg.0
0x5f420  ldfld    int32 System.Xml.DtdParser::curPos
0x5f425  ldc.i4.6
0x5f426  add
0x5f427  stfld    int32 System.Xml.DtdParser::curPos
0x5f42c  ldarg.0
0x5f42d  ldc.i4.s 0x13
0x5f42f  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5f434  ldc.i4.s 0x16
0x5f436  ret
0x5f437  ldarg.0
0x5f438  ldarg.0
0x5f439  ldfld    int32 System.Xml.DtdParser::curPos
0x5f43e  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x5f443  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f448  br.s     loc_5F45B
0x5f44a  ldarg.0
0x5f44b  ldarg.0
0x5f44c  ldfld    int32 System.Xml.DtdParser::curPos
0x5f451  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x5f456  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f45b  ldarg.0
0x5f45c  call     instance int32 System.Xml.DtdParser::ReadData()
0x5f461  brtrue   System.Xml.DtdParser__ScanAttlist6
0x5f466  ldarg.0
0x5f467  ldarg.0
0x5f468  ldfld    int32 System.Xml.DtdParser::curPos
0x5f46d  ldstr    aXmlIncompleted// "Xml_IncompleteDtdContent"
0x5f472  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5f477  br       System.Xml.DtdParser__ScanAttlist6
```
