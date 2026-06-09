# Microsoft.ReportingServices.Diagnostics.Monthly::GetDayRange

- ea: `0xf090`
- end: `0xf19a`
- name: `Microsoft.ReportingServices.Diagnostics.Monthly::GetDayRange`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf030`
- `0xf490`

## callees

- `0xf090`

## pseudocode

```c

```

## disassembly

```asm
0xf090  ldstr    asc_126C2// ""
0xf095  stloc.0
0xf096  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0xf09b  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf0a0  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xf0a5  stloc.1
0xf0a6  ldc.i4.1
0xf0a7  stloc.2
0xf0a8  ldc.i4.0
0xf0a9  stloc.3
0xf0aa  ldc.i4.0
0xf0ab  stloc.s  4
0xf0ad  ldc.i4.1
0xf0ae  stloc.s  5
0xf0b0  br       loc_F179
0xf0b5  ldloc.2
0xf0b6  conv.i8
0xf0b7  ldarg.0
0xf0b8  conv.u8
0xf0b9  and
0xf0ba  ldc.i4.0
0xf0bb  conv.i8
0xf0bc  ble.s    loc_F0D3
0xf0be  ldloc.s  5
0xf0c0  ldc.i4.s 0x20
0xf0c2  beq.s    loc_F0D3
0xf0c4  ldloc.3
0xf0c5  brtrue.s loc_F0CA
0xf0c7  ldloc.s  5
0xf0c9  stloc.3
0xf0ca  ldloc.s  5
0xf0cc  stloc.s  4
0xf0ce  br       loc_F16F
0xf0d3  ldloc.3
0xf0d4  brfalse  loc_F16F
0xf0d9  ldloc.3
0xf0da  ldloc.s  4
0xf0dc  bne.un.s loc_F0F4
0xf0de  ldloc.0
0xf0df  ldloca.s 3
0xf0e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0e6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf0eb  ldloc.1
0xf0ec  call     string [mscorlib]System.String::Concat(string, string, string)
0xf0f1  stloc.0
0xf0f2  br.s     loc_F16D
0xf0f4  ldloc.3
0xf0f5  ldc.i4.1
0xf0f6  add
0xf0f7  ldloc.s  4
0xf0f9  bne.un.s loc_F133
0xf0fb  ldc.i4.5
0xf0fc  newarr   [mscorlib]System.String
0xf101  dup
0xf102  ldc.i4.0
0xf103  ldloc.0
0xf104  stelem.ref
0xf105  dup
0xf106  ldc.i4.1
0xf107  ldloca.s 3
0xf109  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf10e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf113  stelem.ref
0xf114  dup
0xf115  ldc.i4.2
0xf116  ldloc.1
0xf117  stelem.ref
0xf118  dup
0xf119  ldc.i4.3
0xf11a  ldloca.s 4
0xf11c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf121  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf126  stelem.ref
0xf127  dup
0xf128  ldc.i4.4
0xf129  ldloc.1
0xf12a  stelem.ref
0xf12b  call     string [mscorlib]System.String::Concat(string[])
0xf130  stloc.0
0xf131  br.s     loc_F16D
0xf133  ldc.i4.5
0xf134  newarr   [mscorlib]System.String
0xf139  dup
0xf13a  ldc.i4.0
0xf13b  ldloc.0
0xf13c  stelem.ref
0xf13d  dup
0xf13e  ldc.i4.1
0xf13f  ldloca.s 3
0xf141  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf146  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf14b  stelem.ref
0xf14c  dup
0xf14d  ldc.i4.2
0xf14e  ldstr    asc_1665A// "-"
0xf153  stelem.ref
0xf154  dup
0xf155  ldc.i4.3
0xf156  ldloca.s 4
0xf158  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf15d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf162  stelem.ref
0xf163  dup
0xf164  ldc.i4.4
0xf165  ldloc.1
0xf166  stelem.ref
0xf167  call     string [mscorlib]System.String::Concat(string[])
0xf16c  stloc.0
0xf16d  ldc.i4.0
0xf16e  stloc.3
0xf16f  ldloc.2
0xf170  ldc.i4.1
0xf171  shl
0xf172  stloc.2
0xf173  ldloc.s  5
0xf175  ldc.i4.1
0xf176  add
0xf177  stloc.s  5
0xf179  ldloc.s  5
0xf17b  ldc.i4.s 0x21
0xf17d  blt      loc_F0B5
0xf182  ldloc.0
0xf183  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf188  ldc.i4.0
0xf189  ble.s    loc_F198
0xf18b  ldloc.0
0xf18c  ldloc.1
0xf18d  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0xf192  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xf197  stloc.0
0xf198  ldloc.0
0xf199  ret
```
