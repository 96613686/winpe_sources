# Microsoft.ReportingServices.Diagnostics.ScheduleFieldValidation::TryGetDayBitMap

- ea: `0xc090`
- end: `0xc206`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleFieldValidation::TryGetDayBitMap`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf070`

## callees

- `0xc090`

## pseudocode

```c

```

## disassembly

```asm
0xc090  ldarg.3
0xc091  ldc.i4.0
0xc092  stind.i4
0xc093  ldc.i4.0
0xc094  stloc.0
0xc095  ldarg.0
0xc096  ldstr    asc_16656// ","
0xc09b  callvirt instance bool [mscorlib]System.String::Contains(string)
0xc0a0  brtrue.s loc_C0B4
0xc0a2  ldarg.2
0xc0a3  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xc0a8  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xc0ad  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0xc0b2  br.s     loc_C0BE
0xc0b4  ldstr    asc_16656// ","
0xc0b9  call     instance char[] [mscorlib]System.String::ToCharArray()
0xc0be  stloc.1
0xc0bf  ldstr    asc_1665A// "-"
0xc0c4  call     instance char[] [mscorlib]System.String::ToCharArray()
0xc0c9  stloc.2
0xc0ca  ldarg.0
0xc0cb  ldloc.1
0xc0cc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc0d1  stloc.3
0xc0d2  ldloc.3
0xc0d3  ldlen
0xc0d4  brtrue.s loc_C0D8
0xc0d6  ldc.i4.0
0xc0d7  ret
0xc0d8  ldloc.3
0xc0d9  stloc.s  6
0xc0db  ldc.i4.0
0xc0dc  stloc.s  7
0xc0de  br       loc_C1C7
0xc0e3  ldloc.s  6
0xc0e5  ldloc.s  7
0xc0e7  ldelem.ref
0xc0e8  ldloc.2
0xc0e9  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc0ee  stloc.s  8
0xc0f0  ldloc.s  8
0xc0f2  ldlen
0xc0f3  brfalse.s loc_C0FC
0xc0f5  ldloc.s  8
0xc0f7  ldlen
0xc0f8  conv.i4
0xc0f9  ldc.i4.2
0xc0fa  ble.s    loc_C0FE
0xc0fc  ldc.i4.0
0xc0fd  ret
0xc0fe  ldc.i4.0
0xc0ff  stloc.s  9
0xc101  ldc.i4.0
0xc102  stloc.s  0xA
0xc104  ldloc.s  8
0xc106  ldc.i4.0
0xc107  ldelem.ref
0xc108  ldc.i4.7
0xc109  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc10e  ldloca.s 9
0xc110  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xc115  brtrue.s loc_C119
0xc117  ldc.i4.0
0xc118  ret
0xc119  ldloc.s  9
0xc11b  ldc.i4.1
0xc11c  blt.s    loc_C124
0xc11e  ldloc.s  9
0xc120  ldc.i4.s 0x1F
0xc122  ble.s    loc_C126
0xc124  ldc.i4.0
0xc125  ret
0xc126  ldloc.s  9
0xc128  ldloc.0
0xc129  bgt.s    loc_C12E
0xc12b  ldloc.0
0xc12c  br.s     loc_C130
0xc12e  ldloc.s  9
0xc130  stloc.0
0xc131  ldloc.s  8
0xc133  ldlen
0xc134  conv.i4
0xc135  ldc.i4.2
0xc136  bne.un.s loc_C16B
0xc138  ldloc.s  8
0xc13a  ldc.i4.1
0xc13b  ldelem.ref
0xc13c  ldc.i4.7
0xc13d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc142  ldloca.s 0xA
0xc144  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xc149  brtrue.s loc_C14D
0xc14b  ldc.i4.0
0xc14c  ret
0xc14d  ldloc.s  0xA
0xc14f  ldc.i4.1
0xc150  blt.s    loc_C15E
0xc152  ldloc.s  0xA
0xc154  ldc.i4.s 0x1F
0xc156  bgt.s    loc_C15E
0xc158  ldloc.s  0xA
0xc15a  ldloc.s  9
0xc15c  bge.s    loc_C160
0xc15e  ldc.i4.0
0xc15f  ret
0xc160  ldloc.s  0xA
0xc162  ldloc.0
0xc163  bgt.s    loc_C168
0xc165  ldloc.0
0xc166  br.s     loc_C16A
0xc168  ldloc.s  0xA
0xc16a  stloc.0
0xc16b  ldc.i4.1
0xc16c  stloc.s  0xB
0xc16e  ldc.i4.1
0xc16f  stloc.s  0xC
0xc171  br.s     loc_C17F
0xc173  ldloc.s  0xB
0xc175  ldc.i4.1
0xc176  shl
0xc177  stloc.s  0xB
0xc179  ldloc.s  0xC
0xc17b  ldc.i4.1
0xc17c  add
0xc17d  stloc.s  0xC
0xc17f  ldloc.s  0xC
0xc181  ldloc.s  9
0xc183  blt.s    loc_C173
0xc185  ldarg.3
0xc186  ldarg.3
0xc187  ldind.u4
0xc188  ldloc.s  0xB
0xc18a  or
0xc18b  stind.i4
0xc18c  ldloc.s  9
0xc18e  ldc.i4.1
0xc18f  add
0xc190  stloc.s  0xC
0xc192  br.s     loc_C1BB
0xc194  ldc.i4.1
0xc195  stloc.s  0xB
0xc197  ldc.i4.1
0xc198  stloc.s  0xD
0xc19a  br.s     loc_C1A8
0xc19c  ldloc.s  0xB
0xc19e  ldc.i4.1
0xc19f  shl
0xc1a0  stloc.s  0xB
0xc1a2  ldloc.s  0xD
0xc1a4  ldc.i4.1
0xc1a5  add
0xc1a6  stloc.s  0xD
0xc1a8  ldloc.s  0xD
0xc1aa  ldloc.s  0xC
0xc1ac  blt.s    loc_C19C
0xc1ae  ldarg.3
0xc1af  ldarg.3
0xc1b0  ldind.u4
0xc1b1  ldloc.s  0xB
0xc1b3  or
0xc1b4  stind.i4
0xc1b5  ldloc.s  0xC
0xc1b7  ldc.i4.1
0xc1b8  add
0xc1b9  stloc.s  0xC
0xc1bb  ldloc.s  0xC
0xc1bd  ldloc.s  0xA
0xc1bf  ble.s    loc_C194
0xc1c1  ldloc.s  7
0xc1c3  ldc.i4.1
0xc1c4  add
0xc1c5  stloc.s  7
0xc1c7  ldloc.s  7
0xc1c9  ldloc.s  6
0xc1cb  ldlen
0xc1cc  conv.i4
0xc1cd  blt      loc_C0E3
0xc1d2  ldc.i4.1
0xc1d3  stloc.s  4
0xc1d5  ldc.i4.0
0xc1d6  stloc.s  5
0xc1d8  br.s     loc_C1FB
0xc1da  ldarg.1
0xc1db  ldloc.s  4
0xc1dd  and
0xc1de  ldloc.s  4
0xc1e0  bne.un.s loc_C1EF
0xc1e2  ldloc.0
0xc1e3  ldsfld   int32[] Microsoft.ReportingServices.Diagnostics.ScheduleFieldValidation::m_daysInMonth
0xc1e8  ldloc.s  5
0xc1ea  ldelem.i4
0xc1eb  ble.s    loc_C1EF
0xc1ed  ldc.i4.0
0xc1ee  ret
0xc1ef  ldloc.s  4
0xc1f1  ldc.i4.2
0xc1f2  mul
0xc1f3  stloc.s  4
0xc1f5  ldloc.s  5
0xc1f7  ldc.i4.1
0xc1f8  add
0xc1f9  stloc.s  5
0xc1fb  ldloc.s  4
0xc1fd  ldc.i4   0x800
0xc202  ble.s    loc_C1DA
0xc204  ldc.i4.1
0xc205  ret
```
