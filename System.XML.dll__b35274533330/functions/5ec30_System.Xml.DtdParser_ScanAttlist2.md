# System.Xml.DtdParser::ScanAttlist2

- ea: `0x5ec30`
- end: `0x5f0b0`
- name: `System.Xml.DtdParser::ScanAttlist2`
- size: `1152`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5dc90`
- `0x5ec30`

## callees

- `0x15dc0`
- `0x5ec30`
- `0x60940`
- `0x60de0`

## string_xrefs

- `0x5f0a1`: `Xml_IncompleteDtdContent`
- `0x5ecf5`: `Xml_InvalidAttributeType1`
- `0x5ed86`: `Xml_InvalidAttributeType`
- `0x5edd9`: `Xml_InvalidAttributeType`
- `0x5ee0a`: `Xml_InvalidAttributeType`
- `0x5ee4e`: `Xml_InvalidAttributeType`
- `0x5eea8`: `Xml_InvalidAttributeType`
- `0x5ef9e`: `Xml_InvalidAttributeType`
- `0x5f026`: `Xml_InvalidAttributeType`
- `0x5f072`: `Xml_InvalidAttributeType`
- `0x5f085`: `Xml_InvalidAttributeType`

## pseudocode

```c

```

## disassembly

```asm
0x5ec30  ldarg.0
0x5ec31  ldfld    char[] System.Xml.DtdParser::chars
0x5ec36  ldarg.0
0x5ec37  ldfld    int32 System.Xml.DtdParser::curPos
0x5ec3c  ldelem.u2
0x5ec3d  stloc.0
0x5ec3e  ldloc.0
0x5ec3f  ldc.i4.s 0x43
0x5ec41  bgt.un.s loc_5EC52
0x5ec43  ldloc.0
0x5ec44  ldc.i4.s 0x28
0x5ec46  beq.s    loc_5EC6F
0x5ec48  ldloc.0
0x5ec49  ldc.i4.s 0x43
0x5ec4b  beq.s    loc_5EC8F
0x5ec4d  br       loc_5F07E
0x5ec52  ldloc.0
0x5ec53  ldc.i4.s 0x45
0x5ec55  beq      loc_5ED17
0x5ec5a  ldloc.0
0x5ec5b  ldc.i4.s 0x49
0x5ec5d  beq      loc_5EE19
0x5ec62  ldloc.0
0x5ec63  ldc.i4.s 0x4E
0x5ec65  beq      loc_5EEE5
0x5ec6a  br       loc_5F07E
0x5ec6f  ldarg.0
0x5ec70  ldarg.0
0x5ec71  ldfld    int32 System.Xml.DtdParser::curPos
0x5ec76  ldc.i4.1
0x5ec77  add
0x5ec78  stfld    int32 System.Xml.DtdParser::curPos
0x5ec7d  ldarg.0
0x5ec7e  ldc.i4.3
0x5ec7f  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5ec84  ldarg.0
0x5ec85  ldc.i4.s 0x11
0x5ec87  stfld    valuetype ScanningFunction System.Xml.DtdParser::nextScaningFunction
0x5ec8c  ldc.i4.s 0x1B
0x5ec8e  ret
0x5ec8f  ldarg.0
0x5ec90  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5ec95  ldarg.0
0x5ec96  ldfld    int32 System.Xml.DtdParser::curPos
0x5ec9b  sub
0x5ec9c  ldc.i4.5
0x5ec9d  blt      loc_5F08F
0x5eca2  ldarg.0
0x5eca3  ldfld    char[] System.Xml.DtdParser::chars
0x5eca8  ldarg.0
0x5eca9  ldfld    int32 System.Xml.DtdParser::curPos
0x5ecae  ldc.i4.1
0x5ecaf  add
0x5ecb0  ldelem.u2
0x5ecb1  ldc.i4.s 0x44
0x5ecb3  bne.un.s loc_5ECEE
0x5ecb5  ldarg.0
0x5ecb6  ldfld    char[] System.Xml.DtdParser::chars
0x5ecbb  ldarg.0
0x5ecbc  ldfld    int32 System.Xml.DtdParser::curPos
0x5ecc1  ldc.i4.2
0x5ecc2  add
0x5ecc3  ldelem.u2
0x5ecc4  ldc.i4.s 0x41
0x5ecc6  bne.un.s loc_5ECEE
0x5ecc8  ldarg.0
0x5ecc9  ldfld    char[] System.Xml.DtdParser::chars
0x5ecce  ldarg.0
0x5eccf  ldfld    int32 System.Xml.DtdParser::curPos
0x5ecd4  ldc.i4.3
0x5ecd5  add
0x5ecd6  ldelem.u2
0x5ecd7  ldc.i4.s 0x54
0x5ecd9  bne.un.s loc_5ECEE
0x5ecdb  ldarg.0
0x5ecdc  ldfld    char[] System.Xml.DtdParser::chars
0x5ece1  ldarg.0
0x5ece2  ldfld    int32 System.Xml.DtdParser::curPos
0x5ece7  ldc.i4.4
0x5ece8  add
0x5ece9  ldelem.u2
0x5ecea  ldc.i4.s 0x41
0x5ecec  beq.s    loc_5ECFF
0x5ecee  ldarg.0
0x5ecef  ldarg.0
0x5ecf0  ldfld    int32 System.Xml.DtdParser::curPos
0x5ecf5  ldstr    aXmlInvalidattr// "Xml_InvalidAttributeType1"
0x5ecfa  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ecff  ldarg.0
0x5ed00  ldarg.0
0x5ed01  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed06  ldc.i4.5
0x5ed07  add
0x5ed08  stfld    int32 System.Xml.DtdParser::curPos
0x5ed0d  ldarg.0
0x5ed0e  ldc.i4.s 0x12
0x5ed10  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5ed15  ldc.i4.0
0x5ed16  ret
0x5ed17  ldarg.0
0x5ed18  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5ed1d  ldarg.0
0x5ed1e  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed23  sub
0x5ed24  ldc.i4.s 9
0x5ed26  blt      loc_5F08F
0x5ed2b  ldarg.0
0x5ed2c  ldc.i4.s 0x12
0x5ed2e  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5ed33  ldarg.0
0x5ed34  ldfld    char[] System.Xml.DtdParser::chars
0x5ed39  ldarg.0
0x5ed3a  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed3f  ldc.i4.1
0x5ed40  add
0x5ed41  ldelem.u2
0x5ed42  ldc.i4.s 0x4E
0x5ed44  bne.un.s loc_5ED7F
0x5ed46  ldarg.0
0x5ed47  ldfld    char[] System.Xml.DtdParser::chars
0x5ed4c  ldarg.0
0x5ed4d  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed52  ldc.i4.2
0x5ed53  add
0x5ed54  ldelem.u2
0x5ed55  ldc.i4.s 0x54
0x5ed57  bne.un.s loc_5ED7F
0x5ed59  ldarg.0
0x5ed5a  ldfld    char[] System.Xml.DtdParser::chars
0x5ed5f  ldarg.0
0x5ed60  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed65  ldc.i4.3
0x5ed66  add
0x5ed67  ldelem.u2
0x5ed68  ldc.i4.s 0x49
0x5ed6a  bne.un.s loc_5ED7F
0x5ed6c  ldarg.0
0x5ed6d  ldfld    char[] System.Xml.DtdParser::chars
0x5ed72  ldarg.0
0x5ed73  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed78  ldc.i4.4
0x5ed79  add
0x5ed7a  ldelem.u2
0x5ed7b  ldc.i4.s 0x54
0x5ed7d  beq.s    loc_5ED90
0x5ed7f  ldarg.0
0x5ed80  ldarg.0
0x5ed81  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed86  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x5ed8b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ed90  ldarg.0
0x5ed91  ldfld    char[] System.Xml.DtdParser::chars
0x5ed96  ldarg.0
0x5ed97  ldfld    int32 System.Xml.DtdParser::curPos
0x5ed9c  ldc.i4.5
0x5ed9d  add
0x5ed9e  ldelem.u2
0x5ed9f  stloc.1
0x5eda0  ldloc.1
0x5eda1  ldc.i4.s 0x49
0x5eda3  beq.s    loc_5EDAC
0x5eda5  ldloc.1
0x5eda6  ldc.i4.s 0x59
0x5eda8  beq.s    loc_5EDF3
0x5edaa  br.s     loc_5EE03
0x5edac  ldarg.0
0x5edad  ldfld    char[] System.Xml.DtdParser::chars
0x5edb2  ldarg.0
0x5edb3  ldfld    int32 System.Xml.DtdParser::curPos
0x5edb8  ldc.i4.6
0x5edb9  add
0x5edba  ldelem.u2
0x5edbb  ldc.i4.s 0x45
0x5edbd  bne.un.s loc_5EDD2
0x5edbf  ldarg.0
0x5edc0  ldfld    char[] System.Xml.DtdParser::chars
0x5edc5  ldarg.0
0x5edc6  ldfld    int32 System.Xml.DtdParser::curPos
0x5edcb  ldc.i4.7
0x5edcc  add
0x5edcd  ldelem.u2
0x5edce  ldc.i4.s 0x53
0x5edd0  beq.s    loc_5EDE3
0x5edd2  ldarg.0
0x5edd3  ldarg.0
0x5edd4  ldfld    int32 System.Xml.DtdParser::curPos
0x5edd9  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x5edde  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ede3  ldarg.0
0x5ede4  ldarg.0
0x5ede5  ldfld    int32 System.Xml.DtdParser::curPos
0x5edea  ldc.i4.8
0x5edeb  add
0x5edec  stfld    int32 System.Xml.DtdParser::curPos
0x5edf1  ldc.i4.5
0x5edf2  ret
0x5edf3  ldarg.0
0x5edf4  ldarg.0
0x5edf5  ldfld    int32 System.Xml.DtdParser::curPos
0x5edfa  ldc.i4.6
0x5edfb  add
0x5edfc  stfld    int32 System.Xml.DtdParser::curPos
0x5ee01  ldc.i4.4
0x5ee02  ret
0x5ee03  ldarg.0
0x5ee04  ldarg.0
0x5ee05  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee0a  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x5ee0f  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ee14  br       loc_5F08F
0x5ee19  ldarg.0
0x5ee1a  ldfld    int32 System.Xml.DtdParser::charsUsed
0x5ee1f  ldarg.0
0x5ee20  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee25  sub
0x5ee26  ldc.i4.6
0x5ee27  blt      loc_5F08F
0x5ee2c  ldarg.0
0x5ee2d  ldc.i4.s 0x12
0x5ee2f  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x5ee34  ldarg.0
0x5ee35  ldfld    char[] System.Xml.DtdParser::chars
0x5ee3a  ldarg.0
0x5ee3b  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee40  ldc.i4.1
0x5ee41  add
0x5ee42  ldelem.u2
0x5ee43  ldc.i4.s 0x44
0x5ee45  beq.s    loc_5EE58
0x5ee47  ldarg.0
0x5ee48  ldarg.0
0x5ee49  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee4e  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x5ee53  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5ee58  ldarg.0
0x5ee59  ldfld    char[] System.Xml.DtdParser::chars
0x5ee5e  ldarg.0
0x5ee5f  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee64  ldc.i4.2
0x5ee65  add
0x5ee66  ldelem.u2
0x5ee67  ldc.i4.s 0x52
0x5ee69  beq.s    loc_5EE7B
0x5ee6b  ldarg.0
0x5ee6c  ldarg.0
0x5ee6d  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee72  ldc.i4.2
0x5ee73  add
0x5ee74  stfld    int32 System.Xml.DtdParser::curPos
0x5ee79  ldc.i4.1
0x5ee7a  ret
0x5ee7b  ldarg.0
0x5ee7c  ldfld    char[] System.Xml.DtdParser::chars
0x5ee81  ldarg.0
0x5ee82  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee87  ldc.i4.3
0x5ee88  add
0x5ee89  ldelem.u2
0x5ee8a  ldc.i4.s 0x45
0x5ee8c  bne.un.s loc_5EEA1
0x5ee8e  ldarg.0
0x5ee8f  ldfld    char[] System.Xml.DtdParser::chars
0x5ee94  ldarg.0
0x5ee95  ldfld    int32 System.Xml.DtdParser::curPos
0x5ee9a  ldc.i4.4
0x5ee9b  add
0x5ee9c  ldelem.u2
0x5ee9d  ldc.i4.s 0x46
0x5ee9f  beq.s    loc_5EEB2
0x5eea1  ldarg.0
0x5eea2  ldarg.0
0x5eea3  ldfld    int32 System.Xml.DtdParser::curPos
0x5eea8  ldstr    aXmlInvalidattr_0// "Xml_InvalidAttributeType"
0x5eead  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5eeb2  ldarg.0
0x5eeb3  ldfld    char[] System.Xml.DtdParser::chars
0x5eeb8  ldarg.0
0x5eeb9  ldfld    int32 System.Xml.DtdParser::curPos
0x5eebe  ldc.i4.5
0x5eebf  add
0x5eec0  ldelem.u2
0x5eec1  ldc.i4.s 0x53
0x5eec3  beq.s    loc_5EED5
0x5eec5  ldarg.0
0x5eec6  ldarg.0
0x5eec7  ldfld    int32 System.Xml.DtdParser::curPos
0x5eecc  ldc.i4.5
0x5eecd  add
0x5eece  stfld    int32 System.Xml.DtdParser::curPos
0x5eed3  ldc.i4.2
0x5eed4  ret
0x5eed5  ldarg.0
0x5eed6  ldarg.0
0x5eed7  ldfld    int32 System.Xml.DtdParser::curPos
0x5eedc  ldc.i4.6
0x5eedd  add
0x5eede  stfld    int32 System.Xml.DtdParser::curPos
0x5eee3  ldc.i4.3
0x5eee4  ret
0x5eee5  ldarg.0
  ... truncated ...
```
