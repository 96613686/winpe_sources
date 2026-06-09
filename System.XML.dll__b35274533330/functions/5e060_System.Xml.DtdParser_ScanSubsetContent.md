# System.Xml.DtdParser::ScanSubsetContent

- ea: `0x5e060`
- end: `0x5e594`
- name: `System.Xml.DtdParser::ScanSubsetContent`
- size: `1332`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5dc90`
- `0x5e060`

## callees

- `0x15dc0`
- `0x5e060`
- `0x60940`
- `0x60de0`

## string_xrefs

- `0x5e176`: `Xml_ExpectDtdMarkup`
- `0x5e21c`: `Xml_ExpectDtdMarkup`
- `0x5e259`: `Xml_ExpectDtdMarkup`
- `0x5e2f3`: `Xml_ExpectDtdMarkup`
- `0x5e3bf`: `Xml_ExpectDtdMarkup`
- `0x5e441`: `Xml_ExpectDtdMarkup`
- `0x5e46c`: `Xml_ExpectDtdMarkup`
- `0x5e4a6`: `Xml_ExpectDtdMarkup`
- `0x5e569`: `Xml_ExpectDtdMarkup`
- `0x5e585`: `Xml_IncompleteDtdContent`

## pseudocode

```c

```

## disassembly

```asm
0x5e060  ldarg.0
0x5e061  ldfld    char[] System.Xml.DtdParser::chars
0x5e066  ldarg.0
0x5e067  ldfld    int32 System.Xml.DtdParser::curPos
0x5e06c  ldelem.u2
0x5e06d  stloc.0
0x5e06e  ldloc.0
0x5e06f  ldc.i4.s 0x3C
0x5e071  beq.s    loc_5E080
0x5e073  ldloc.0
0x5e074  ldc.i4.s 0x5D
0x5e076  beq      loc_5E4B3
0x5e07b  br       loc_5E553
0x5e080  ldarg.0
0x5e081  ldfld    char[] System.Xml.DtdParser::chars
0x5e086  ldarg.0
0x5e087  ldfld    int32 System.Xml.DtdParser::curPos
0x5e08c  ldc.i4.1
0x5e08d  add
0x5e08e  ldelem.u2
0x5e08f  stloc.1
0x5e090  ldloc.1
0x5e091  ldc.i4.s 0x21
0x5e093  beq.s    loc_5E0A2
0x5e095  ldloc.1
0x5e096  ldc.i4.s 0x3F
0x5e098  beq      loc_5E47B
0x5e09d  br       loc_5E48C
0x5e0a2  ldarg.0
0x5e0a3  ldfld    char[] System.Xml.DtdParser::chars
0x5e0a8  ldarg.0
0x5e0a9  ldfld    int32 System.Xml.DtdParser::curPos
0x5e0ae  ldc.i4.2
0x5e0af  add
0x5e0b0  ldelem.u2
0x5e0b1  stloc.2
0x5e0b2  ldloc.2
0x5e0b3  ldc.i4.s 0x41
0x5e0b5  bgt.un.s loc_5E0CC
0x5e0b7  ldloc.2
0x5e0b8  ldc.i4.s 0x2D
0x5e0ba  beq      loc_5E403
0x5e0bf  ldloc.2
0x5e0c0  ldc.i4.s 0x41
0x5e0c2  beq      loc_5E266
0x5e0c7  br       loc_5E450
0x5e0cc  ldloc.2
0x5e0cd  ldc.i4.s 0x45
0x5e0cf  beq.s    loc_5E0E6
0x5e0d1  ldloc.2
0x5e0d2  ldc.i4.s 0x4E
0x5e0d4  beq      loc_5E31E
0x5e0d9  ldloc.2
0x5e0da  ldc.i4.s 0x5B
0x5e0dc  beq      loc_5E3EA
0x5e0e1  br       loc_5E450
0x5e0e6  ldarg.0
0x5e0e7  ldfld    char[] System.Xml.DtdParser::chars
0x5e0ec  ldarg.0
0x5e0ed  ldfld    int32 System.Xml.DtdParser::curPos
0x5e0f2  ldc.i4.3
0x5e0f3  add
0x5e0f4  ldelem.u2
0x5e0f5  ldc.i4.s 0x4C
0x5e0f7  bne.un   loc_5E1A0
0x5e0fc  ldarg.0
0x5e0fd  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5e102  ldarg.0
0x5e103  ldfld    int32 System.Xml.DtdParser::curPos
0x5e108  sub
0x5e109  ldc.i4.s 9
0x5e10b  blt      loc_5E573
0x5e110  ldarg.0
0x5e111  ldfld    char[] System.Xml.DtdParser::chars
0x5e116  ldarg.0
0x5e117  ldfld    int32 System.Xml.DtdParser::curPos
0x5e11c  ldc.i4.4
0x5e11d  add
0x5e11e  ldelem.u2
0x5e11f  ldc.i4.s 0x45
0x5e121  bne.un.s loc_5E16F
0x5e123  ldarg.0
0x5e124  ldfld    char[] System.Xml.DtdParser::chars
0x5e129  ldarg.0
0x5e12a  ldfld    int32 System.Xml.DtdParser::curPos
0x5e12f  ldc.i4.5
0x5e130  add
0x5e131  ldelem.u2
0x5e132  ldc.i4.s 0x4D
0x5e134  bne.un.s loc_5E16F
0x5e136  ldarg.0
0x5e137  ldfld    char[] System.Xml.DtdParser::chars
0x5e13c  ldarg.0
0x5e13d  ldfld    int32 System.Xml.DtdParser::curPos
0x5e142  ldc.i4.6
0x5e143  add
0x5e144  ldelem.u2
0x5e145  ldc.i4.s 0x45
0x5e147  bne.un.s loc_5E16F
0x5e149  ldarg.0
0x5e14a  ldfld    char[] System.Xml.DtdParser::chars
0x5e14f  ldarg.0
0x5e150  ldfld    int32 System.Xml.DtdParser::curPos
0x5e155  ldc.i4.7
0x5e156  add
0x5e157  ldelem.u2
0x5e158  ldc.i4.s 0x4E
0x5e15a  bne.un.s loc_5E16F
0x5e15c  ldarg.0
0x5e15d  ldfld    char[] System.Xml.DtdParser::chars
0x5e162  ldarg.0
0x5e163  ldfld    int32 System.Xml.DtdParser::curPos
0x5e168  ldc.i4.8
0x5e169  add
0x5e16a  ldelem.u2
0x5e16b  ldc.i4.s 0x54
0x5e16d  beq.s    loc_5E180
0x5e16f  ldarg.0
0x5e170  ldarg.0
0x5e171  ldfld    int32 System.Xml.DtdParser::curPos
0x5e176  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x5e17b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5e180  ldarg.0
0x5e181  ldarg.0
0x5e182  ldfld    int32 System.Xml.DtdParser::curPos
0x5e187  ldc.i4.s 9
0x5e189  add
0x5e18a  stfld    int32 System.Xml.DtdParser::curPos
0x5e18f  ldarg.0
0x5e190  ldc.i4.2
0x5e191  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5e196  ldarg.0
0x5e197  ldc.i4.6
0x5e198  stfld    valuetype ScanningFunction System.Xml.DtdParser::nextScaningFunction
0x5e19d  ldc.i4.s 0xC
0x5e19f  ret
0x5e1a0  ldarg.0
0x5e1a1  ldfld    char[] System.Xml.DtdParser::chars
0x5e1a6  ldarg.0
0x5e1a7  ldfld    int32 System.Xml.DtdParser::curPos
0x5e1ac  ldc.i4.3
0x5e1ad  add
0x5e1ae  ldelem.u2
0x5e1af  ldc.i4.s 0x4E
0x5e1b1  bne.un   loc_5E23F
0x5e1b6  ldarg.0
0x5e1b7  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5e1bc  ldarg.0
0x5e1bd  ldfld    int32 System.Xml.DtdParser::curPos
0x5e1c2  sub
0x5e1c3  ldc.i4.8
0x5e1c4  blt      loc_5E573
0x5e1c9  ldarg.0
0x5e1ca  ldfld    char[] System.Xml.DtdParser::chars
0x5e1cf  ldarg.0
0x5e1d0  ldfld    int32 System.Xml.DtdParser::curPos
0x5e1d5  ldc.i4.4
0x5e1d6  add
0x5e1d7  ldelem.u2
0x5e1d8  ldc.i4.s 0x54
0x5e1da  bne.un.s loc_5E215
0x5e1dc  ldarg.0
0x5e1dd  ldfld    char[] System.Xml.DtdParser::chars
0x5e1e2  ldarg.0
0x5e1e3  ldfld    int32 System.Xml.DtdParser::curPos
0x5e1e8  ldc.i4.5
0x5e1e9  add
0x5e1ea  ldelem.u2
0x5e1eb  ldc.i4.s 0x49
0x5e1ed  bne.un.s loc_5E215
0x5e1ef  ldarg.0
0x5e1f0  ldfld    char[] System.Xml.DtdParser::chars
0x5e1f5  ldarg.0
0x5e1f6  ldfld    int32 System.Xml.DtdParser::curPos
0x5e1fb  ldc.i4.6
0x5e1fc  add
0x5e1fd  ldelem.u2
0x5e1fe  ldc.i4.s 0x54
0x5e200  bne.un.s loc_5E215
0x5e202  ldarg.0
0x5e203  ldfld    char[] System.Xml.DtdParser::chars
0x5e208  ldarg.0
0x5e209  ldfld    int32 System.Xml.DtdParser::curPos
0x5e20e  ldc.i4.7
0x5e20f  add
0x5e210  ldelem.u2
0x5e211  ldc.i4.s 0x59
0x5e213  beq.s    loc_5E226
0x5e215  ldarg.0
0x5e216  ldarg.0
0x5e217  ldfld    int32 System.Xml.DtdParser::curPos
0x5e21c  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x5e221  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5e226  ldarg.0
0x5e227  ldarg.0
0x5e228  ldfld    int32 System.Xml.DtdParser::curPos
0x5e22d  ldc.i4.8
0x5e22e  add
0x5e22f  stfld    int32 System.Xml.DtdParser::curPos
0x5e234  ldarg.0
0x5e235  ldc.i4.s 0x14
0x5e237  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5e23c  ldc.i4.s 0xD
0x5e23e  ret
0x5e23f  ldarg.0
0x5e240  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5e245  ldarg.0
0x5e246  ldfld    int32 System.Xml.DtdParser::curPos
0x5e24b  sub
0x5e24c  ldc.i4.4
0x5e24d  blt      loc_5E573
0x5e252  ldarg.0
0x5e253  ldarg.0
0x5e254  ldfld    int32 System.Xml.DtdParser::curPos
0x5e259  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x5e25e  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5e263  ldc.i4.s 9
0x5e265  ret
0x5e266  ldarg.0
0x5e267  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5e26c  ldarg.0
0x5e26d  ldfld    int32 System.Xml.DtdParser::curPos
0x5e272  sub
0x5e273  ldc.i4.s 9
0x5e275  blt      loc_5E573
0x5e27a  ldarg.0
0x5e27b  ldfld    char[] System.Xml.DtdParser::chars
0x5e280  ldarg.0
0x5e281  ldfld    int32 System.Xml.DtdParser::curPos
0x5e286  ldc.i4.3
0x5e287  add
0x5e288  ldelem.u2
0x5e289  ldc.i4.s 0x54
0x5e28b  bne.un.s loc_5E2EC
0x5e28d  ldarg.0
0x5e28e  ldfld    char[] System.Xml.DtdParser::chars
0x5e293  ldarg.0
0x5e294  ldfld    int32 System.Xml.DtdParser::curPos
0x5e299  ldc.i4.4
0x5e29a  add
0x5e29b  ldelem.u2
0x5e29c  ldc.i4.s 0x54
0x5e29e  bne.un.s loc_5E2EC
0x5e2a0  ldarg.0
0x5e2a1  ldfld    char[] System.Xml.DtdParser::chars
0x5e2a6  ldarg.0
0x5e2a7  ldfld    int32 System.Xml.DtdParser::curPos
0x5e2ac  ldc.i4.5
0x5e2ad  add
0x5e2ae  ldelem.u2
0x5e2af  ldc.i4.s 0x4C
0x5e2b1  bne.un.s loc_5E2EC
0x5e2b3  ldarg.0
0x5e2b4  ldfld    char[] System.Xml.DtdParser::chars
0x5e2b9  ldarg.0
0x5e2ba  ldfld    int32 System.Xml.DtdParser::curPos
0x5e2bf  ldc.i4.6
0x5e2c0  add
0x5e2c1  ldelem.u2
0x5e2c2  ldc.i4.s 0x49
0x5e2c4  bne.un.s loc_5E2EC
0x5e2c6  ldarg.0
0x5e2c7  ldfld    char[] System.Xml.DtdParser::chars
0x5e2cc  ldarg.0
0x5e2cd  ldfld    int32 System.Xml.DtdParser::curPos
0x5e2d2  ldc.i4.7
0x5e2d3  add
0x5e2d4  ldelem.u2
0x5e2d5  ldc.i4.s 0x53
0x5e2d7  bne.un.s loc_5E2EC
0x5e2d9  ldarg.0
0x5e2da  ldfld    char[] System.Xml.DtdParser::chars
0x5e2df  ldarg.0
0x5e2e0  ldfld    int32 System.Xml.DtdParser::curPos
0x5e2e5  ldc.i4.8
0x5e2e6  add
0x5e2e7  ldelem.u2
0x5e2e8  ldc.i4.s 0x54
0x5e2ea  beq.s    loc_5E2FD
0x5e2ec  ldarg.0
0x5e2ed  ldarg.0
0x5e2ee  ldfld    int32 System.Xml.DtdParser::curPos
0x5e2f3  ldstr    aXmlExpectdtdma// "Xml_ExpectDtdMarkup"
0x5e2f8  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5e2fd  ldarg.0
0x5e2fe  ldarg.0
0x5e2ff  ldfld    int32 System.Xml.DtdParser::curPos
0x5e304  ldc.i4.s 9
0x5e306  add
0x5e307  stfld    int32 System.Xml.DtdParser::curPos
0x5e30c  ldarg.0
0x5e30d  ldc.i4.2
0x5e30e  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5e313  ldarg.0
0x5e314  ldc.i4.s 0xD
0x5e316  stfld    valuetype ScanningFunction System.Xml.DtdParser::nextScaningFunction
0x5e31b  ldc.i4.s 0xB
0x5e31d  ret
0x5e31e  ldarg.0
0x5e31f  ldfld    int32 System.Xml.DtdParser::charsUsed
  ... truncated ...
```
