# FullTextLine::FormatLine

- ea: `0x156940`
- end: `0x156c28`
- name: `FullTextLine::FormatLine`
- size: `744`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: ``

## callers

- `0x156810`
- `0x156ff0`

## callees

- `0x2dd70`
- `0xef6d0`
- `0xef700`
- `0xef810`
- `0xef990`
- `0xefc10`
- `0xefe20`
- `0xeff60`
- `0x11b8c0`
- `0x11b8e0`
- `0x11bc90`
- `0x11c210`
- `0x11c7b0`
- `0x11c800`
- `0x11cdd0`
- `0x11cde0`
- `0x11cdf0`
- `0x11ce00`
- `0x124f60`
- `0x125060`
- `0x1250e0`
- `0x125120`
- `0x1256f0`
- `0x125820`
- `0x125830`
- `0x126cd0`
- `0x127e20`
- `0x127e50`
- `0x127e60`
- `0x146e70`
- `0x156940`
- `0x156c30`
- `0x156d00`

## string_xrefs

- `0x156a8f`: `CreateLineFailure`

## pseudocode

```c

```

## disassembly

```asm
0x156940  ldarg.0
0x156941  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156946  ldarg.1
0x156947  callvirt instance class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.FullTextState::get_Formatter()
0x15694c  stfld    class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.TextMetrics::_formatter
0x156951  ldarg.1
0x156952  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::get_TextStore()
0x156957  stloc.3
0x156958  ldarg.1
0x156959  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::get_TextMarkerStore()
0x15695e  stloc.s  0xA
0x156960  ldloc.3
0x156961  callvirt instance class MS.Internal.TextFormatting.FormatSettings MS.Internal.TextFormatting.TextStore::get_Settings()
0x156966  stloc.s  9
0x156968  ldloc.s  9
0x15696a  callvirt instance class MS.Internal.TextFormatting.ParaProp MS.Internal.TextFormatting.FormatSettings::get_Pap()
0x15696f  stloc.s  6
0x156971  ldarg.0
0x156972  ldloc.s  6
0x156974  callvirt instance class System.Windows.TextDecorationCollection MS.Internal.TextFormatting.ParaProp::get_TextDecorations()
0x156979  stfld    class System.Windows.TextDecorationCollection FullTextLine::_paragraphTextDecorations
0x15697e  ldarg.0
0x15697f  ldfld    class System.Windows.TextDecorationCollection FullTextLine::_paragraphTextDecorations
0x156984  brfalse.s loc_1569A9
0x156986  ldarg.0
0x156987  ldfld    class System.Windows.TextDecorationCollection FullTextLine::_paragraphTextDecorations
0x15698c  callvirt instance int32 System.Windows.TextDecorationCollection::get_Count()
0x156991  brfalse.s loc_1569A2
0x156993  ldarg.0
0x156994  ldloc.s  6
0x156996  callvirt instance class System.Windows.Media.Brush MS.Internal.TextFormatting.ParaProp::get_DefaultTextDecorationsBrush()
0x15699b  stfld    class System.Windows.Media.Brush FullTextLine::_defaultTextDecorationsBrush
0x1569a0  br.s     loc_1569A9
0x1569a2  ldarg.0
0x1569a3  ldnull
0x1569a4  stfld    class System.Windows.TextDecorationCollection FullTextLine::_paragraphTextDecorations
0x1569a9  ldarg.0
0x1569aa  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x1569af  ldfld    class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.TextMetrics::_formatter
0x1569b4  ldarg.1
0x1569b5  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1569ba  callvirt instance class System.Windows.Media.TextFormatting.TextFormatterContext MS.Internal.TextFormatting.TextFormatterImp::AcquireContext(object owner, native int ploc)
0x1569bf  stloc.0
0x1569c0  ldloca.s 0xF
0x1569c2  initobj  MS.Internal.TextFormatting.LsLInfo
0x1569c8  ldloca.s 0xE
0x1569ca  initobj  MS.Internal.TextFormatting.LsLineWidths
0x1569d0  ldarg.1
0x1569d1  ldloc.0
0x1569d2  callvirt instance void MS.Internal.TextFormatting.FullTextState::SetTabs(class System.Windows.Media.TextFormatting.TextFormatterContext context)
0x1569d7  ldc.i4.0
0x1569d8  stloc.s  5
0x1569da  ldarg.3
0x1569db  ldc.i4.0
0x1569dc  ble.s    loc_1569E9
0x1569de  ldarg.0
0x1569df  ldloc.3
0x1569e0  ldarg.2
0x1569e1  ldarg.3
0x1569e2  call     instance int32 FullTextLine::PrefetchLSRuns(class MS.Internal.TextFormatting.TextStore store, int32 cpFirst, int32 lineLength)
0x1569e7  stloc.s  5
0x1569e9  ldloc.0
0x1569ea  ldarg.2
0x1569eb  ldloc.s  5
0x1569ed  ldarg.s  4
0x1569ef  ldarg.s  7
0x1569f1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1569f6  ldloca.s 0xD
0x1569f8  ldloca.s 0xF
0x1569fa  ldarg.0
0x1569fb  ldflda   int32 FullTextLine::_depthQueryMax
0x156a00  ldloca.s 0xE
0x156a02  callvirt instance valuetype MS.Internal.TextFormatting.LsErr System.Windows.Media.TextFormatting.TextFormatterContext::CreateLine(int32 cpFirst, int32 lineLength, int32 maxWidth, valuetype MS.Internal.TextFormatting.LineFlags lineFlags, native int previousLineBreakRecord, [out] native int& ploline, [out] valuetype MS.Internal.TextFormatting.LsLInfo& plslineInfo, [out] int32& maxDepth, [out] valuetype MS.Internal.TextFormatting.LsLineWidths& lineWidths)
0x156a07  stloc.1
0x156a08  ldloc.1
0x156a09  ldc.i4.s 0xCF
0x156a0b  bne.un.s loc_156A5F
0x156a0d  ldarg.1
0x156a0e  callvirt instance int32 MS.Internal.TextFormatting.FullTextState::get_CpMeasured()
0x156a13  stloc.2
0x156a14  ldc.i4.1
0x156a15  stloc.s  4
0x156a17  ldloc.2
0x156a18  ldc.i4.1
0x156a19  bge.s    loc_156A1D
0x156a1b  ldc.i4.1
0x156a1c  stloc.2
0x156a1d  ldloc.3
0x156a1e  ldloc.2
0x156a1f  callvirt instance bool MS.Internal.TextFormatting.TextStore::InsertFakeLineBreak(int32 cpLimit)
0x156a24  pop
0x156a25  ldloc.0
0x156a26  ldarg.2
0x156a27  ldloc.s  5
0x156a29  ldarg.s  4
0x156a2b  ldarg.s  7
0x156a2d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x156a32  ldloca.s 0xD
0x156a34  ldloca.s 0xF
0x156a36  ldarg.0
0x156a37  ldflda   int32 FullTextLine::_depthQueryMax
0x156a3c  ldloca.s 0xE
0x156a3e  callvirt instance valuetype MS.Internal.TextFormatting.LsErr System.Windows.Media.TextFormatting.TextFormatterContext::CreateLine(int32 cpFirst, int32 lineLength, int32 maxWidth, valuetype MS.Internal.TextFormatting.LineFlags lineFlags, native int previousLineBreakRecord, [out] native int& ploline, [out] valuetype MS.Internal.TextFormatting.LsLInfo& plslineInfo, [out] int32& maxDepth, [out] valuetype MS.Internal.TextFormatting.LsLineWidths& lineWidths)
0x156a43  stloc.1
0x156a44  ldloc.1
0x156a45  ldc.i4.s 0xCF
0x156a47  bne.un.s loc_156A5F
0x156a49  ldloc.2
0x156a4a  ldc.i4.1
0x156a4b  beq.s    loc_156A5F
0x156a4d  ldarg.1
0x156a4e  callvirt instance int32 MS.Internal.TextFormatting.FullTextState::get_CpMeasured()
0x156a53  ldloc.s  4
0x156a55  sub
0x156a56  stloc.2
0x156a57  ldloc.s  4
0x156a59  ldc.i4.2
0x156a5a  mul
0x156a5b  stloc.s  4
0x156a5d  br.s     loc_156A17
0x156a5f  ldarg.0
0x156a60  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> FullTextLine::_ploline
0x156a65  ldloc.s  0xD
0x156a67  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::set_Value(var<u1>)
0x156a6c  ldloc.0
0x156a6d  callvirt instance class [mscorlib]System.Exception System.Windows.Media.TextFormatting.TextFormatterContext::get_CallbackException()
0x156a72  stloc.s  8
0x156a74  ldloc.0
0x156a75  callvirt instance void System.Windows.Media.TextFormatting.TextFormatterContext::Release()
0x156a7a  ldloc.1
0x156a7b  brfalse.s loc_156AAE
0x156a7d  ldarg.0
0x156a7e  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x156a83  ldloc.s  8
0x156a85  brfalse.s loc_156A8F
0x156a87  ldloc.s  8
0x156a89  call     class [mscorlib]System.Exception FullTextLine::WrapException(class [mscorlib]System.Exception caughtException)
0x156a8e  throw
0x156a8f  ldstr    aCreatelinefail// "CreateLineFailure"
0x156a94  ldc.i4.1
0x156a95  newarr   [mscorlib]System.Object
0x156a9a  dup
0x156a9b  ldc.i4.0
0x156a9c  ldloc.1
0x156a9d  box      MS.Internal.TextFormatting.LsErr
0x156aa2  stelem.ref
0x156aa3  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x156aa8  ldloc.1
0x156aa9  call     void System.Windows.Media.TextFormatting.TextFormatterContext::ThrowExceptionFromLsError(string message, valuetype MS.Internal.TextFormatting.LsErr lserr)
0x156aae  ldloc.0
0x156aaf  call     void [mscorlib]System.GC::KeepAlive(object)
0x156ab4  ldarg.0
0x156ab5  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156aba  ldarg.1
0x156abb  ldarg.2
0x156abc  ldarg.s  6
0x156abe  ldarg.s  8
0x156ac0  ldloca.s 0xE
0x156ac2  ldloca.s 0xF
0x156ac4  conv.u
0x156ac5  call     instance void MS.Internal.TextFormatting.TextMetrics::Compute(class MS.Internal.TextFormatting.FullTextState fullText, int32 firstCharIndex, int32 paragraphWidth, class MS.Internal.TextFormatting.FormattedTextSymbols collapsingSymbol, valuetype MS.Internal.TextFormatting.LsLineWidths& lineWidths, valuetype MS.Internal.TextFormatting.LsLInfo* plsLineInfo)
0x156aca  ldarg.0
0x156acb  ldloc.s  0xE
0x156acd  ldfld    int32 MS.Internal.TextFormatting.LsLineWidths::upMinStartTrailing
0x156ad2  ldarg.0
0x156ad3  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156ad8  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_textStart
0x156add  sub
0x156ade  stfld    int32 FullTextLine::_textMinWidthAtTrailing
0x156ae3  ldarg.s  8
0x156ae5  brfalse.s loc_156B0D
0x156ae7  ldarg.0
0x156ae8  ldarg.s  8
0x156aea  stfld    class MS.Internal.TextFormatting.FormattedTextSymbols FullTextLine::_collapsingSymbol
0x156aef  ldarg.0
0x156af0  ldarg.0
0x156af1  ldfld    int32 FullTextLine::_textMinWidthAtTrailing
0x156af6  ldarg.s  8
0x156af8  callvirt instance float64 MS.Internal.TextFormatting.FormattedTextSymbols::get_Width()
0x156afd  call     int32 MS.Internal.TextFormatting.TextFormatterImp::RealToIdeal(float64 i)
0x156b02  add
0x156b03  stfld    int32 FullTextLine::_textMinWidthAtTrailing
0x156b08  br       loc_156B8A
0x156b0d  ldarg.0
0x156b0e  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156b13  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_textStart
0x156b18  ldarg.0
0x156b19  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156b1e  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_textWidthAtTrailing
0x156b23  add
0x156b24  ldarg.s  5
0x156b26  ble.s    loc_156B8A
0x156b28  ldc.i4.1
0x156b29  stloc.s  7
0x156b2b  ldarg.0
0x156b2c  ldfld    valuetype System.Windows.Media.TextFormattingMode FullTextLine::_textFormattingMode
0x156b31  ldc.i4.1
0x156b32  bne.un.s loc_156B71
0x156b34  ldarg.0
0x156b35  callvirt instance float64 System.Windows.Media.TextFormatting.TextLine::get_Width()
0x156b3a  stloc.s  0xC
0x156b3c  ldarg.0
0x156b3d  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156b42  ldfld    class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.TextMetrics::_formatter
0x156b47  ldarg.s  5
0x156b49  conv.r8
0x156b4a  ldarg.0
0x156b4b  call     instance float64 System.Windows.Media.TextFormatting.TextLine::get_PixelsPerDip()
0x156b50  callvirt instance float64 MS.Internal.TextFormatting.TextFormatterImp::IdealToReal(float64 i, float64 pixelsPerDip)
0x156b55  stloc.s  0xB
0x156b57  ldloc.s  0xC
0x156b59  ldloc.s  0xB
0x156b5b  ldarg.0
0x156b5c  call     instance float64 System.Windows.Media.TextFormatting.TextLine::get_PixelsPerDip()
0x156b61  ldarg.0
0x156b62  ldfld    valuetype System.Windows.Media.TextFormattingMode FullTextLine::_textFormattingMode
0x156b67  call     int32 MS.Internal.TextFormatting.TextFormatterImp::CompareReal(float64 x, float64 y, float64 pixelsPerDip, valuetype System.Windows.Media.TextFormattingMode mode)
0x156b6c  ldc.i4.0
0x156b6d  cgt
0x156b6f  stloc.s  7
0x156b71  ldloc.s  7
0x156b73  brfalse.s loc_156B8A
0x156b75  ldarg.0
0x156b76  ldarg.0
0x156b77  ldfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156b7c  ldc.i4.2
0x156b7d  or
0x156b7e  stfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156b83  ldarg.0
0x156b84  ldarg.1
0x156b85  stfld    class MS.Internal.TextFormatting.FullTextState FullTextLine::_fullText
0x156b8a  ldarg.1
0x156b8b  brfalse.s loc_156BA7
0x156b8d  ldarg.1
0x156b8e  callvirt instance bool MS.Internal.TextFormatting.FullTextState::get_KeepState()
0x156b93  brtrue.s loc_156BA0
0x156b95  ldarg.0
0x156b96  ldfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156b9b  ldc.i4.s 0x20
0x156b9d  and
0x156b9e  brfalse.s loc_156BA7
0x156ba0  ldarg.0
0x156ba1  ldarg.1
0x156ba2  stfld    class MS.Internal.TextFormatting.FullTextState FullTextLine::_fullText
0x156ba7  ldarg.0
0x156ba8  ldloc.0
0x156ba9  callvirt instance valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextFormatterContext::get_Ploc()
0x156bae  stfld    valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> FullTextLine::_ploc
0x156bb3  ldarg.0
0x156bb4  ldarg.2
0x156bb5  stfld    int32 FullTextLine::_cpFirst
0x156bba  ldarg.0
0x156bbb  ldarg.s  6
0x156bbd  stfld    int32 FullTextLine::_paragraphWidth
0x156bc2  ldloc.s  6
0x156bc4  callvirt instance bool MS.Internal.TextFormatting.ParaProp::get_RightToLeft()
0x156bc9  brfalse.s loc_156BD9
0x156bcb  ldarg.0
0x156bcc  ldarg.0
0x156bcd  ldfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156bd2  ldc.i4.8
0x156bd3  or
0x156bd4  stfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156bd9  ldloc.s  0xF
0x156bdb  ldfld    int32 MS.Internal.TextFormatting.LsLInfo::fForcedBreak
0x156be0  brfalse.s loc_156BF1
0x156be2  ldarg.0
0x156be3  ldarg.0
0x156be4  ldfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156be9  ldc.i4.s 0x40
0x156beb  or
0x156bec  stfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156bf1  ldarg.0
0x156bf2  ldloc.3
0x156bf3  callvirt instance class MS.Internal.SpanVector MS.Internal.TextFormatting.TextStore::get_PlsrunVector()
0x156bf8  stfld    class MS.Internal.SpanVector FullTextLine::_plsrunVector
0x156bfd  ldarg.0
0x156bfe  ldloc.3
0x156bff  callvirt instance class [mscorlib]System.Collections.ArrayList MS.Internal.TextFormatting.TextStore::get_LsrunList()
0x156c04  stfld    class [mscorlib]System.Collections.ArrayList FullTextLine::_lsrunsMainText
0x156c09  ldloc.s  0xA
0x156c0b  brfalse.s loc_156C1A
0x156c0d  ldarg.0
0x156c0e  ldloc.s  0xA
0x156c10  callvirt instance class [mscorlib]System.Collections.ArrayList MS.Internal.TextFormatting.TextStore::get_LsrunList()
0x156c15  stfld    class [mscorlib]System.Collections.ArrayList FullTextLine::_lsrunsMarkerText
0x156c1a  ldarg.0
0x156c1b  ldloc.s  9
0x156c1d  callvirt instance class System.Windows.Media.TextFormatting.TextSource MS.Internal.TextFormatting.FormatSettings::get_TextSource()
0x156c22  stfld    class System.Windows.Media.TextFormatting.TextSource FullTextLine::_textSource
0x156c27  ret
```
