# Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round3

- ea: `0xbe0`
- end: `0xfa7`
- name: `Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round3`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e0`

## callees

- `0x490`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0xbe0  ldc.i4.s 0x10
0xbe2  ldarg.1
0xbe3  mul
0xbe4  stloc.0
0xbe5  ldarg.0
0xbe6  ldarg.0
0xbe7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xbec  ldarg.0
0xbed  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xbf2  ldarg.0
0xbf3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xbf8  ldarg.0
0xbf9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xbfe  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xc03  add
0xc04  ldarg.0
0xc05  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xc0a  ldloc.0
0xc0b  ldelem.i4
0xc0c  add
0xc0d  ldc.i4   0x6ED9EBA1
0xc12  add
0xc13  ldc.i4.3
0xc14  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xc19  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xc1e  ldarg.0
0xc1f  ldarg.0
0xc20  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xc25  ldarg.0
0xc26  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xc2b  ldarg.0
0xc2c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xc31  ldarg.0
0xc32  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xc37  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xc3c  add
0xc3d  ldarg.0
0xc3e  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xc43  ldc.i4.8
0xc44  ldloc.0
0xc45  add
0xc46  ldelem.i4
0xc47  add
0xc48  ldc.i4   0x6ED9EBA1
0xc4d  add
0xc4e  ldc.i4.s 9
0xc50  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xc55  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xc5a  ldarg.0
0xc5b  ldarg.0
0xc5c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xc61  ldarg.0
0xc62  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xc67  ldarg.0
0xc68  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xc6d  ldarg.0
0xc6e  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xc73  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xc78  add
0xc79  ldarg.0
0xc7a  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xc7f  ldc.i4.4
0xc80  ldloc.0
0xc81  add
0xc82  ldelem.i4
0xc83  add
0xc84  ldc.i4   0x6ED9EBA1
0xc89  add
0xc8a  ldc.i4.s 0xB
0xc8c  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xc91  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xc96  ldarg.0
0xc97  ldarg.0
0xc98  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xc9d  ldarg.0
0xc9e  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xca3  ldarg.0
0xca4  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xca9  ldarg.0
0xcaa  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xcaf  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xcb4  add
0xcb5  ldarg.0
0xcb6  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xcbb  ldc.i4.s 0xC
0xcbd  ldloc.0
0xcbe  add
0xcbf  ldelem.i4
0xcc0  add
0xcc1  ldc.i4   0x6ED9EBA1
0xcc6  add
0xcc7  ldc.i4.s 0xF
0xcc9  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xcce  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xcd3  ldarg.0
0xcd4  ldarg.0
0xcd5  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xcda  ldarg.0
0xcdb  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xce0  ldarg.0
0xce1  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xce6  ldarg.0
0xce7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xcec  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xcf1  add
0xcf2  ldarg.0
0xcf3  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xcf8  ldc.i4.2
0xcf9  ldloc.0
0xcfa  add
0xcfb  ldelem.i4
0xcfc  add
0xcfd  ldc.i4   0x6ED9EBA1
0xd02  add
0xd03  ldc.i4.3
0xd04  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xd09  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xd0e  ldarg.0
0xd0f  ldarg.0
0xd10  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xd15  ldarg.0
0xd16  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xd1b  ldarg.0
0xd1c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xd21  ldarg.0
0xd22  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xd27  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xd2c  add
0xd2d  ldarg.0
0xd2e  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xd33  ldc.i4.s 0xA
0xd35  ldloc.0
0xd36  add
0xd37  ldelem.i4
0xd38  add
0xd39  ldc.i4   0x6ED9EBA1
0xd3e  add
0xd3f  ldc.i4.s 9
0xd41  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xd46  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xd4b  ldarg.0
0xd4c  ldarg.0
0xd4d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xd52  ldarg.0
0xd53  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xd58  ldarg.0
0xd59  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xd5e  ldarg.0
0xd5f  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xd64  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xd69  add
0xd6a  ldarg.0
0xd6b  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xd70  ldc.i4.6
0xd71  ldloc.0
0xd72  add
0xd73  ldelem.i4
0xd74  add
0xd75  ldc.i4   0x6ED9EBA1
0xd7a  add
0xd7b  ldc.i4.s 0xB
0xd7d  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xd82  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xd87  ldarg.0
0xd88  ldarg.0
0xd89  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xd8e  ldarg.0
0xd8f  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xd94  ldarg.0
0xd95  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xd9a  ldarg.0
0xd9b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xda0  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xda5  add
0xda6  ldarg.0
0xda7  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xdac  ldc.i4.s 0xE
0xdae  ldloc.0
0xdaf  add
0xdb0  ldelem.i4
0xdb1  add
0xdb2  ldc.i4   0x6ED9EBA1
0xdb7  add
0xdb8  ldc.i4.s 0xF
0xdba  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xdbf  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xdc4  ldarg.0
0xdc5  ldarg.0
0xdc6  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xdcb  ldarg.0
0xdcc  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xdd1  ldarg.0
0xdd2  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xdd7  ldarg.0
0xdd8  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xddd  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xde2  add
0xde3  ldarg.0
0xde4  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xde9  ldc.i4.1
0xdea  ldloc.0
0xdeb  add
0xdec  ldelem.i4
0xded  add
0xdee  ldc.i4   0x6ED9EBA1
0xdf3  add
0xdf4  ldc.i4.3
0xdf5  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xdfa  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xdff  ldarg.0
0xe00  ldarg.0
0xe01  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xe06  ldarg.0
0xe07  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xe0c  ldarg.0
0xe0d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xe12  ldarg.0
0xe13  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xe18  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xe1d  add
0xe1e  ldarg.0
0xe1f  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xe24  ldc.i4.s 9
0xe26  ldloc.0
0xe27  add
0xe28  ldelem.i4
0xe29  add
0xe2a  ldc.i4   0x6ED9EBA1
0xe2f  add
0xe30  ldc.i4.s 9
0xe32  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xe37  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xe3c  ldarg.0
0xe3d  ldarg.0
0xe3e  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xe43  ldarg.0
0xe44  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xe49  ldarg.0
0xe4a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xe4f  ldarg.0
0xe50  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xe55  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xe5a  add
0xe5b  ldarg.0
0xe5c  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xe61  ldc.i4.5
0xe62  ldloc.0
0xe63  add
0xe64  ldelem.i4
0xe65  add
0xe66  ldc.i4   0x6ED9EBA1
0xe6b  add
0xe6c  ldc.i4.s 0xB
0xe6e  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xe73  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xe78  ldarg.0
0xe79  ldarg.0
0xe7a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xe7f  ldarg.0
0xe80  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xe85  ldarg.0
0xe86  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xe8b  ldarg.0
0xe8c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xe91  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xe96  add
0xe97  ldarg.0
0xe98  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xe9d  ldc.i4.s 0xD
0xe9f  ldloc.0
0xea0  add
0xea1  ldelem.i4
0xea2  add
0xea3  ldc.i4   0x6ED9EBA1
0xea8  add
0xea9  ldc.i4.s 0xF
0xeab  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xeb0  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xeb5  ldarg.0
0xeb6  ldarg.0
0xeb7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xebc  ldarg.0
0xebd  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xec2  ldarg.0
0xec3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xec8  ldarg.0
0xec9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xece  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::H(int32 x, int32 y, int32 z)
0xed3  add
0xed4  ldarg.0
0xed5  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xeda  ldc.i4.3
0xedb  ldloc.0
0xedc  add
0xedd  ldelem.i4
0xede  add
0xedf  ldc.i4   0x6ED9EBA1
0xee4  add
0xee5  ldc.i4.3
0xee6  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
  ... truncated ...
```
