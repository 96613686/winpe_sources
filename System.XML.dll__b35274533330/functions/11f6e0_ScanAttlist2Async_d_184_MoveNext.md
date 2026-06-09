# <ScanAttlist2Async>d__184::MoveNext

- ea: `0x11f6e0`
- end: `0x11fc3d`
- name: `<ScanAttlist2Async>d__184::MoveNext`
- size: `1373`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15dc0`
- `0x60de0`
- `0x61d30`
- `0x11f6e0`

## string_xrefs

- `0x11fc00`: `Xml_IncompleteDtdContent`
- `0x11f7be`: `Xml_InvalidAttributeType1`
- `0x11f854`: `Xml_InvalidAttributeType`
- `0x11f8aa`: `Xml_InvalidAttributeType`
- `0x11f8e5`: `Xml_InvalidAttributeType`
- `0x11f929`: `Xml_InvalidAttributeType`
- `0x11f988`: `Xml_InvalidAttributeType`
- `0x11fa8b`: `Xml_InvalidAttributeType`
- `0x11fb18`: `Xml_InvalidAttributeType`
- `0x11fb6e`: `Xml_InvalidAttributeType`
- `0x11fb81`: `Xml_InvalidAttributeType`

## pseudocode

```c

```

## disassembly

```asm
0x11f6e0  ldarg.0
0x11f6e1  ldfld    int32 <ScanAttlist2Async>d__184::<>1__state
0x11f6e6  stloc.0
0x11f6e7  ldarg.0
0x11f6e8  ldfld    class System.Xml.DtdParser <ScanAttlist2Async>d__184::<>4__this
0x11f6ed  stloc.1
0x11f6ee  ldloc.0
0x11f6ef  brfalse  loc_11FBCC
0x11f6f4  ldloc.1
0x11f6f5  ldfld    char[] System.Xml.DtdParser::chars
0x11f6fa  ldloc.1
0x11f6fb  ldfld    int32 System.Xml.DtdParser::curPos
0x11f700  ldelem.u2
0x11f701  stloc.3
0x11f702  ldloc.3
0x11f703  ldc.i4.s 0x43
0x11f705  bgt.un.s loc_11F716
0x11f707  ldloc.3
0x11f708  ldc.i4.s 0x28
0x11f70a  beq.s    loc_11F733
0x11f70c  ldloc.3
0x11f70d  ldc.i4.s 0x43
0x11f70f  beq.s    loc_11F758
0x11f711  br       loc_11FB7A
0x11f716  ldloc.3
0x11f717  ldc.i4.s 0x45
0x11f719  beq      loc_11F7E5
0x11f71e  ldloc.3
0x11f71f  ldc.i4.s 0x49
0x11f721  beq      loc_11F8F4
0x11f726  ldloc.3
0x11f727  ldc.i4.s 0x4E
0x11f729  beq      loc_11F9CF
0x11f72e  br       loc_11FB7A
0x11f733  ldloc.1
0x11f734  ldloc.1
0x11f735  ldfld    int32 System.Xml.DtdParser::curPos
0x11f73a  ldc.i4.1
0x11f73b  add
0x11f73c  stfld    int32 System.Xml.DtdParser::curPos
0x11f741  ldloc.1
0x11f742  ldc.i4.3
0x11f743  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11f748  ldloc.1
0x11f749  ldc.i4.s 0x11
0x11f74b  stfld    valuetype ScanningFunction System.Xml.DtdParser::nextScaningFunction
0x11f750  ldc.i4.s 0x1B
0x11f752  stloc.2
0x11f753  leave    loc_11FC28
0x11f758  ldloc.1
0x11f759  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11f75e  ldloc.1
0x11f75f  ldfld    int32 System.Xml.DtdParser::curPos
0x11f764  sub
0x11f765  ldc.i4.5
0x11f766  blt      loc_11FB8B
0x11f76b  ldloc.1
0x11f76c  ldfld    char[] System.Xml.DtdParser::chars
0x11f771  ldloc.1
0x11f772  ldfld    int32 System.Xml.DtdParser::curPos
0x11f777  ldc.i4.1
0x11f778  add
0x11f779  ldelem.u2
0x11f77a  ldc.i4.s 0x44
0x11f77c  bne.un.s loc_11F7B7
0x11f77e  ldloc.1
0x11f77f  ldfld    char[] System.Xml.DtdParser::chars
0x11f784  ldloc.1
0x11f785  ldfld    int32 System.Xml.DtdParser::curPos
0x11f78a  ldc.i4.2
0x11f78b  add
0x11f78c  ldelem.u2
0x11f78d  ldc.i4.s 0x41
0x11f78f  bne.un.s loc_11F7B7
0x11f791  ldloc.1
0x11f792  ldfld    char[] System.Xml.DtdParser::chars
0x11f797  ldloc.1
0x11f798  ldfld    int32 System.Xml.DtdParser::curPos
0x11f79d  ldc.i4.3
0x11f79e  add
0x11f79f  ldelem.u2
0x11f7a0  ldc.i4.s 0x54
0x11f7a2  bne.un.s loc_11F7B7
0x11f7a4  ldloc.1
0x11f7a5  ldfld    char[] System.Xml.DtdParser::chars
0x11f7aa  ldloc.1
0x11f7ab  ldfld    int32 System.Xml.DtdParser::curPos
0x11f7b0  ldc.i4.4
0x11f7b1  add
0x11f7b2  ldelem.u2
0x11f7b3  ldc.i4.s 0x41
0x11f7b5  beq.s    loc_11F7C8
0x11f7b7  ldloc.1
0x11f7b8  ldloc.1
0x11f7b9  ldfld    int32 System.Xml.DtdParser::curPos
0x11f7be  ldstr    aXmlInvalidattr// "Xml_InvalidAttributeType1"
0x11f7c3  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f7c8  ldloc.1
0x11f7c9  ldloc.1
0x11f7ca  ldfld    int32 System.Xml.DtdParser::curPos
0x11f7cf  ldc.i4.5
0x11f7d0  add
0x11f7d1  stfld    int32 System.Xml.DtdParser::curPos
0x11f7d6  ldloc.1
0x11f7d7  ldc.i4.s 0x12
0x11f7d9  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11f7de  ldc.i4.0
0x11f7df  stloc.2
0x11f7e0  leave    loc_11FC28
0x11f7e5  ldloc.1
0x11f7e6  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11f7eb  ldloc.1
0x11f7ec  ldfld    int32 System.Xml.DtdParser::curPos
0x11f7f1  sub
0x11f7f2  ldc.i4.s 9
0x11f7f4  blt      loc_11FB8B
0x11f7f9  ldloc.1
0x11f7fa  ldc.i4.s 0x12
0x11f7fc  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11f801  ldloc.1
0x11f802  ldfld    char[] System.Xml.DtdParser::chars
0x11f807  ldloc.1
0x11f808  ldfld    int32 System.Xml.DtdParser::curPos
0x11f80d  ldc.i4.1
0x11f80e  add
0x11f80f  ldelem.u2
0x11f810  ldc.i4.s 0x4E
0x11f812  bne.un.s loc_11F84D
0x11f814  ldloc.1
0x11f815  ldfld    char[] System.Xml.DtdParser::chars
0x11f81a  ldloc.1
0x11f81b  ldfld    int32 System.Xml.DtdParser::curPos
0x11f820  ldc.i4.2
0x11f821  add
0x11f822  ldelem.u2
0x11f823  ldc.i4.s 0x54
0x11f825  bne.un.s loc_11F84D
0x11f827  ldloc.1
0x11f828  ldfld    char[] System.Xml.DtdParser::chars
0x11f82d  ldloc.1
0x11f82e  ldfld    int32 System.Xml.DtdParser::curPos
0x11f833  ldc.i4.3
0x11f834  add
0x11f835  ldelem.u2
0x11f836  ldc.i4.s 0x49
0x11f838  bne.un.s loc_11F84D
0x11f83a  ldloc.1
0x11f83b  ldfld    char[] System.Xml.DtdParser::chars
0x11f840  ldloc.1
0x11f841  ldfld    int32 System.Xml.DtdParser::curPos
0x11f846  ldc.i4.4
0x11f847  add
0x11f848  ldelem.u2
0x11f849  ldc.i4.s 0x54
0x11f84b  beq.s    loc_11F85E
0x11f84d  ldloc.1
0x11f84e  ldloc.1
0x11f84f  ldfld    int32 System.Xml.DtdParser::curPos
0x11f854  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x11f859  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f85e  ldloc.1
0x11f85f  ldfld    char[] System.Xml.DtdParser::chars
0x11f864  ldloc.1
0x11f865  ldfld    int32 System.Xml.DtdParser::curPos
0x11f86a  ldc.i4.5
0x11f86b  add
0x11f86c  ldelem.u2
0x11f86d  stloc.s  4
0x11f86f  ldloc.s  4
0x11f871  ldc.i4.s 0x49
0x11f873  beq.s    loc_11F87D
0x11f875  ldloc.s  4
0x11f877  ldc.i4.s 0x59
0x11f879  beq.s    loc_11F8C9
0x11f87b  br.s     loc_11F8DE
0x11f87d  ldloc.1
0x11f87e  ldfld    char[] System.Xml.DtdParser::chars
0x11f883  ldloc.1
0x11f884  ldfld    int32 System.Xml.DtdParser::curPos
0x11f889  ldc.i4.6
0x11f88a  add
0x11f88b  ldelem.u2
0x11f88c  ldc.i4.s 0x45
0x11f88e  bne.un.s loc_11F8A3
0x11f890  ldloc.1
0x11f891  ldfld    char[] System.Xml.DtdParser::chars
0x11f896  ldloc.1
0x11f897  ldfld    int32 System.Xml.DtdParser::curPos
0x11f89c  ldc.i4.7
0x11f89d  add
0x11f89e  ldelem.u2
0x11f89f  ldc.i4.s 0x53
0x11f8a1  beq.s    loc_11F8B4
0x11f8a3  ldloc.1
0x11f8a4  ldloc.1
0x11f8a5  ldfld    int32 System.Xml.DtdParser::curPos
0x11f8aa  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x11f8af  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f8b4  ldloc.1
0x11f8b5  ldloc.1
0x11f8b6  ldfld    int32 System.Xml.DtdParser::curPos
0x11f8bb  ldc.i4.8
0x11f8bc  add
0x11f8bd  stfld    int32 System.Xml.DtdParser::curPos
0x11f8c2  ldc.i4.5
0x11f8c3  stloc.2
0x11f8c4  leave    loc_11FC28
0x11f8c9  ldloc.1
0x11f8ca  ldloc.1
0x11f8cb  ldfld    int32 System.Xml.DtdParser::curPos
0x11f8d0  ldc.i4.6
0x11f8d1  add
0x11f8d2  stfld    int32 System.Xml.DtdParser::curPos
0x11f8d7  ldc.i4.4
0x11f8d8  stloc.2
0x11f8d9  leave    loc_11FC28
0x11f8de  ldloc.1
0x11f8df  ldloc.1
0x11f8e0  ldfld    int32 System.Xml.DtdParser::curPos
0x11f8e5  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x11f8ea  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f8ef  br       loc_11FB8B
0x11f8f4  ldloc.1
0x11f8f5  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11f8fa  ldloc.1
0x11f8fb  ldfld    int32 System.Xml.DtdParser::curPos
0x11f900  sub
0x11f901  ldc.i4.6
0x11f902  blt      loc_11FB8B
0x11f907  ldloc.1
0x11f908  ldc.i4.s 0x12
0x11f90a  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11f90f  ldloc.1
0x11f910  ldfld    char[] System.Xml.DtdParser::chars
0x11f915  ldloc.1
0x11f916  ldfld    int32 System.Xml.DtdParser::curPos
0x11f91b  ldc.i4.1
0x11f91c  add
0x11f91d  ldelem.u2
0x11f91e  ldc.i4.s 0x44
0x11f920  beq.s    loc_11F933
0x11f922  ldloc.1
0x11f923  ldloc.1
0x11f924  ldfld    int32 System.Xml.DtdParser::curPos
0x11f929  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x11f92e  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f933  ldloc.1
0x11f934  ldfld    char[] System.Xml.DtdParser::chars
0x11f939  ldloc.1
0x11f93a  ldfld    int32 System.Xml.DtdParser::curPos
0x11f93f  ldc.i4.2
0x11f940  add
0x11f941  ldelem.u2
0x11f942  ldc.i4.s 0x52
0x11f944  beq.s    loc_11F95B
0x11f946  ldloc.1
0x11f947  ldloc.1
0x11f948  ldfld    int32 System.Xml.DtdParser::curPos
0x11f94d  ldc.i4.2
0x11f94e  add
0x11f94f  stfld    int32 System.Xml.DtdParser::curPos
0x11f954  ldc.i4.1
0x11f955  stloc.2
0x11f956  leave    loc_11FC28
0x11f95b  ldloc.1
0x11f95c  ldfld    char[] System.Xml.DtdParser::chars
0x11f961  ldloc.1
0x11f962  ldfld    int32 System.Xml.DtdParser::curPos
0x11f967  ldc.i4.3
0x11f968  add
0x11f969  ldelem.u2
0x11f96a  ldc.i4.s 0x45
0x11f96c  bne.un.s loc_11F981
0x11f96e  ldloc.1
0x11f96f  ldfld    char[] System.Xml.DtdParser::chars
0x11f974  ldloc.1
0x11f975  ldfld    int32 System.Xml.DtdParser::curPos
0x11f97a  ldc.i4.4
0x11f97b  add
0x11f97c  ldelem.u2
0x11f97d  ldc.i4.s 0x46
0x11f97f  beq.s    loc_11F992
0x11f981  ldloc.1
0x11f982  ldloc.1
0x11f983  ldfld    int32 System.Xml.DtdParser::curPos
0x11f988  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x11f98d  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11f992  ldloc.1
0x11f993  ldfld    char[] System.Xml.DtdParser::chars
0x11f998  ldloc.1
0x11f999  ldfld    int32 System.Xml.DtdParser::curPos
0x11f99e  ldc.i4.5
0x11f99f  add
0x11f9a0  ldelem.u2
0x11f9a1  ldc.i4.s 0x53
0x11f9a3  beq.s    loc_11F9BA
0x11f9a5  ldloc.1
0x11f9a6  ldloc.1
0x11f9a7  ldfld    int32 System.Xml.DtdParser::curPos
0x11f9ac  ldc.i4.5
  ... truncated ...
```
