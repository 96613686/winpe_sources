# MS.Internal.TextFormatting.FullTextBreakpoint::CreateMultiple

- ea: `0x11bde0`
- end: `0x11bf10`
- name: `MS.Internal.TextFormatting.FullTextBreakpoint::CreateMultiple`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0xf0400`

## callees

- `0xef6d0`
- `0xef700`
- `0xef850`
- `0xef990`
- `0xf0160`
- `0xf0500`
- `0xf0510`
- `0x11b8b0`
- `0x11b8d0`
- `0x11b900`
- `0x11bde0`
- `0x11bf10`
- `0x11c800`
- `0x11cae0`
- `0x11cde0`
- `0x124f60`
- `0x127e20`
- `0x127e40`
- `0x146e70`

## string_xrefs

- `0x11beb7`: `CreateBreaksFailure`

## pseudocode

```c

```

## disassembly

```asm
0x11bde0  ldarg.0
0x11bde1  ldnull
0x11bde2  cgt.un
0x11bde4  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11bde9  ldarg.0
0x11bdea  callvirt instance class MS.Internal.TextFormatting.FullTextState System.Windows.Media.TextFormatting.TextParagraphCache::get_FullText()
0x11bdef  stloc.0
0x11bdf0  ldloc.0
0x11bdf1  ldnull
0x11bdf2  cgt.un
0x11bdf4  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11bdf9  ldloc.0
0x11bdfa  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::get_TextStore()
0x11bdff  callvirt instance class MS.Internal.TextFormatting.FormatSettings MS.Internal.TextFormatting.TextStore::get_Settings()
0x11be04  stloc.1
0x11be05  ldloc.1
0x11be06  ldnull
0x11be07  cgt.un
0x11be09  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11be0e  ldloc.1
0x11be0f  ldarg.2
0x11be10  ldarg.3
0x11be11  ldarg.1
0x11be12  ldloc.0
0x11be13  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::get_TextStore()
0x11be18  callvirt instance int32 MS.Internal.TextFormatting.TextStore::get_CpFirst()
0x11be1d  ceq
0x11be1f  callvirt instance void MS.Internal.TextFormatting.FormatSettings::UpdateSettingsForCurrentLine(int32 maxLineWidth, class System.Windows.Media.TextFormatting.TextLineBreak previousLineBreak, bool isFirstLineInPara)
0x11be24  ldloc.1
0x11be25  callvirt instance class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.FormatSettings::get_Formatter()
0x11be2a  ldnull
0x11be2b  cgt.un
0x11be2d  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11be32  ldloc.1
0x11be33  callvirt instance class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.FormatSettings::get_Formatter()
0x11be38  ldloc.0
0x11be39  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x11be3e  callvirt instance class System.Windows.Media.TextFormatting.TextFormatterContext MS.Internal.TextFormatting.TextFormatterImp::AcquireContext(object owner, native int ploc)
0x11be43  stloc.3
0x11be44  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x11be49  stloc.s  8
0x11be4b  ldloc.1
0x11be4c  callvirt instance class System.Windows.Media.TextFormatting.TextLineBreak MS.Internal.TextFormatting.FormatSettings::get_PreviousLineBreak()
0x11be51  brfalse.s loc_11BE69
0x11be53  ldloc.1
0x11be54  callvirt instance class System.Windows.Media.TextFormatting.TextLineBreak MS.Internal.TextFormatting.FormatSettings::get_PreviousLineBreak()
0x11be59  callvirt instance valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextLineBreak::get_BreakRecord()
0x11be5e  stloc.s  9
0x11be60  ldloca.s 9
0x11be62  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0x11be67  stloc.s  8
0x11be69  ldloc.0
0x11be6a  ldloc.3
0x11be6b  callvirt instance void MS.Internal.TextFormatting.FullTextState::SetTabs(class System.Windows.Media.TextFormatting.TextFormatterContext context)
0x11be70  ldloca.s 7
0x11be72  initobj  MS.Internal.TextFormatting.LsBreaks
0x11be78  ldloc.3
0x11be79  ldloc.0
0x11be7a  ldarg.1
0x11be7b  callvirt instance int32 MS.Internal.TextFormatting.FullTextState::GetBreakpointInternalCp(int32 cp)
0x11be80  ldloc.s  8
0x11be82  ldarg.0
0x11be83  callvirt instance valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextParagraphCache::get_Ploparabreak()
0x11be88  stloc.s  9
0x11be8a  ldloca.s 9
0x11be8c  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0x11be91  ldarg.s  4
0x11be93  ldloca.s 7
0x11be95  ldarg.s  5
0x11be97  callvirt instance valuetype MS.Internal.TextFormatting.LsErr System.Windows.Media.TextFormatting.TextFormatterContext::CreateBreaks(int32 cpFirst, native int previousLineBreakRecord, native int ploparabreak, native int ptslinevariantRestriction, valuetype MS.Internal.TextFormatting.LsBreaks& lsbreaks, [out] int32& bestFitIndex)
0x11be9c  stloc.s  4
0x11be9e  ldloc.3
0x11be9f  callvirt instance class [mscorlib]System.Exception System.Windows.Media.TextFormatting.TextFormatterContext::get_CallbackException()
0x11bea4  stloc.s  6
0x11bea6  ldloc.3
0x11bea7  callvirt instance void System.Windows.Media.TextFormatting.TextFormatterContext::Release()
0x11beac  ldloc.s  4
0x11beae  brfalse.s loc_11BED8
0x11beb0  ldloc.s  6
0x11beb2  brfalse.s loc_11BEB7
0x11beb4  ldloc.s  6
0x11beb6  throw
0x11beb7  ldstr    aCreatebreaksfa// "CreateBreaksFailure"
0x11bebc  ldc.i4.1
0x11bebd  newarr   [mscorlib]System.Object
0x11bec2  dup
0x11bec3  ldc.i4.0
0x11bec4  ldloc.s  4
0x11bec6  box      MS.Internal.TextFormatting.LsErr
0x11becb  stelem.ref
0x11becc  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x11bed1  ldloc.s  4
0x11bed3  call     void System.Windows.Media.TextFormatting.TextFormatterContext::ThrowExceptionFromLsError(string message, valuetype MS.Internal.TextFormatting.LsErr lserr)
0x11bed8  ldloc.3
0x11bed9  call     void [mscorlib]System.GC::KeepAlive(object)
0x11bede  ldloc.s  7
0x11bee0  ldfld    int32 MS.Internal.TextFormatting.LsBreaks::cBreaks
0x11bee5  newarr   System.Windows.Media.TextFormatting.TextBreakpoint
0x11beea  stloc.s  5
0x11beec  ldc.i4.0
0x11beed  stloc.2
0x11beee  br.s     loc_11BF03
0x11bef0  ldloc.s  5
0x11bef2  ldloc.2
0x11bef3  ldloc.0
0x11bef4  ldarg.1
0x11bef5  ldarg.2
0x11bef6  ldloca.s 7
0x11bef8  ldloc.2
0x11bef9  newobj   instance void MS.Internal.TextFormatting.FullTextBreakpoint::.ctor(class MS.Internal.TextFormatting.FullTextState fullText, int32 firstCharIndex, int32 maxLineWidth, valuetype MS.Internal.TextFormatting.LsBreaks& lsbreaks, int32 breakIndex)
0x11befe  stelem.ref
0x11beff  ldloc.2
0x11bf00  ldc.i4.1
0x11bf01  add
0x11bf02  stloc.2
0x11bf03  ldloc.2
0x11bf04  ldloc.s  7
0x11bf06  ldfld    int32 MS.Internal.TextFormatting.LsBreaks::cBreaks
0x11bf0b  blt.s    loc_11BEF0
0x11bf0d  ldloc.s  5
0x11bf0f  ret
```
