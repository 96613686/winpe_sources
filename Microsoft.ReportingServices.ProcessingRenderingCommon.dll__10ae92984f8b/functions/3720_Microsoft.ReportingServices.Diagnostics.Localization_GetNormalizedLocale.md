# Microsoft.ReportingServices.Diagnostics.Localization::GetNormalizedLocale

- ea: `0x3720`
- end: `0x380d`
- name: `Microsoft.ReportingServices.Diagnostics.Localization::GetNormalizedLocale`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x3620`
- `0x3810`

## callees

- `0x36b0`
- `0x36d0`
- `0x3720`

## pseudocode

```c

```

## disassembly

```asm
0x3720  ldarg.0
0x3721  ldc.i4.s 0x3B
0x3723  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x3728  stloc.0
0x3729  ldloc.0
0x372a  ldc.i4.m1
0x372b  beq.s    loc_3737
0x372d  ldarg.0
0x372e  ldc.i4.0
0x372f  ldloc.0
0x3730  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x3735  starg.s  0
0x3737  ldarg.0
0x3738  callvirt instance string [mscorlib]System.String::Trim()
0x373d  starg.s  0
0x373f  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.Localization::m_validatedLocaleNames
0x3744  ldarg.0
0x3745  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x374a  brfalse.s loc_375D
0x374c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.Localization::m_validatedLocaleNames
0x3751  ldarg.0
0x3752  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3757  castclass [mscorlib]System.String
0x375c  ret
0x375d  ldarg.0
0x375e  call     bool Microsoft.ReportingServices.Diagnostics.Localization::IsLocaleMatchCulture(string locale)
0x3763  brfalse.s loc_376E
0x3765  ldarg.0
0x3766  ldarg.0
0x3767  call     void Microsoft.ReportingServices.Diagnostics.Localization::AddLocaleToValidatedList(string locale, string normalizedLocale)
0x376c  ldarg.0
0x376d  ret
0x376e  ldarg.0
0x376f  stloc.1
0x3770  ldarg.0
0x3771  ldc.i4.1
0x3772  newarr   [mscorlib]System.Char
0x3777  dup
0x3778  ldc.i4.0
0x3779  ldc.i4.s 0x2D
0x377b  stelem.i2
0x377c  ldc.i4.1
0x377d  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x3782  stloc.2
0x3783  ldloc.2
0x3784  ldlen
0x3785  conv.i4
0x3786  ldc.i4.3
0x3787  bne.un.s loc_379C
0x3789  ldloc.2
0x378a  ldc.i4.0
0x378b  ldelem.ref
0x378c  ldstr    asc_1B46A// "-"
0x3791  ldloc.2
0x3792  ldc.i4.2
0x3793  ldelem.ref
0x3794  call     string [mscorlib]System.String::Concat(string, string, string)
0x3799  stloc.1
0x379a  br.s     loc_37EA
0x379c  ldloc.2
0x379d  ldlen
0x379e  conv.i4
0x379f  ldc.i4.4
0x37a0  bne.un.s loc_37C4
0x37a2  ldloc.2
0x37a3  ldc.i4.2
0x37a4  ldelem.ref
0x37a5  ldstr    aX// "x"
0x37aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37af  brfalse.s loc_37C4
0x37b1  ldloc.2
0x37b2  ldc.i4.0
0x37b3  ldelem.ref
0x37b4  ldstr    asc_1B46A// "-"
0x37b9  ldloc.2
0x37ba  ldc.i4.1
0x37bb  ldelem.ref
0x37bc  call     string [mscorlib]System.String::Concat(string, string, string)
0x37c1  stloc.1
0x37c2  br.s     loc_37EA
0x37c4  ldloc.2
0x37c5  ldlen
0x37c6  conv.i4
0x37c7  ldc.i4.5
0x37c8  bne.un.s loc_37EA
0x37ca  ldloc.2
0x37cb  ldc.i4.3
0x37cc  ldelem.ref
0x37cd  ldstr    aX// "x"
0x37d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x37d7  brfalse.s loc_37EA
0x37d9  ldloc.2
0x37da  ldc.i4.0
0x37db  ldelem.ref
0x37dc  ldstr    asc_1B46A// "-"
0x37e1  ldloc.2
0x37e2  ldc.i4.2
0x37e3  ldelem.ref
0x37e4  call     string [mscorlib]System.String::Concat(string, string, string)
0x37e9  stloc.1
0x37ea  ldloc.1
0x37eb  ldarg.0
0x37ec  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x37f1  brfalse.s loc_3804
0x37f3  ldloc.1
0x37f4  call     bool Microsoft.ReportingServices.Diagnostics.Localization::IsLocaleMatchCulture(string locale)
0x37f9  brfalse.s loc_3804
0x37fb  ldarg.0
0x37fc  ldloc.1
0x37fd  call     void Microsoft.ReportingServices.Diagnostics.Localization::AddLocaleToValidatedList(string locale, string normalizedLocale)
0x3802  ldloc.1
0x3803  ret
0x3804  ldarg.0
0x3805  ldarg.0
0x3806  call     void Microsoft.ReportingServices.Diagnostics.Localization::AddLocaleToValidatedList(string locale, string normalizedLocale)
0x380b  ldarg.0
0x380c  ret
```
