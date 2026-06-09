# System.Windows.Media.TextFormatting.TextParagraphCache::.ctor

- ea: `0xf02f0`
- end: `0xf03ce`
- name: `System.Windows.Media.TextFormatting.TextParagraphCache::.ctor`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x124c30`

## callees

- `0xef6d0`
- `0xef700`
- `0xef890`
- `0xef990`
- `0xf02f0`
- `0x11b8b0`
- `0x11b960`
- `0x11c710`
- `0x11c800`
- `0x124f60`
- `0x146e70`

## string_xrefs

- `0xf037c`: `CreateParaBreakingSessionFailure`
- `0xf039c`: `CreateParaBreakingSessionFailure`

## pseudocode

```c

```

## disassembly

```asm
0xf02f0  ldarg.0
0xf02f1  call     instance void [mscorlib]System.Object::.ctor()
0xf02f6  ldarg.1
0xf02f7  ldnull
0xf02f8  cgt.un
0xf02fa  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0xf02ff  ldarg.0
0xf0300  ldarg.1
0xf0301  ldarg.3
0xf0302  callvirt instance int32 MS.Internal.TextFormatting.FormatSettings::GetFiniteFormatWidth(int32 paragraphWidth)
0xf0307  stfld    int32 System.Windows.Media.TextFormatting.TextParagraphCache::_finiteFormatWidth
0xf030c  ldarg.0
0xf030d  ldarg.1
0xf030e  ldarg.2
0xf030f  ldarg.0
0xf0310  ldfld    int32 System.Windows.Media.TextFormatting.TextParagraphCache::_finiteFormatWidth
0xf0315  call     class MS.Internal.TextFormatting.FullTextState MS.Internal.TextFormatting.FullTextState::Create(class MS.Internal.TextFormatting.FormatSettings settings, int32 cpFirst, int32 finiteFormatWidth)
0xf031a  stfld    class MS.Internal.TextFormatting.FullTextState System.Windows.Media.TextFormatting.TextParagraphCache::_fullText
0xf031f  ldarg.1
0xf0320  callvirt instance class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.FormatSettings::get_Formatter()
0xf0325  ldarg.0
0xf0326  ldfld    class MS.Internal.TextFormatting.FullTextState System.Windows.Media.TextFormatting.TextParagraphCache::_fullText
0xf032b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xf0330  callvirt instance class System.Windows.Media.TextFormatting.TextFormatterContext MS.Internal.TextFormatting.TextFormatterImp::AcquireContext(object owner, native int ploc)
0xf0335  stloc.0
0xf0336  ldarg.0
0xf0337  ldfld    class MS.Internal.TextFormatting.FullTextState System.Windows.Media.TextFormatting.TextParagraphCache::_fullText
0xf033c  ldloc.0
0xf033d  callvirt instance void MS.Internal.TextFormatting.FullTextState::SetTabs(class System.Windows.Media.TextFormatting.TextFormatterContext context)
0xf0342  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xf0347  stloc.3
0xf0348  ldloc.0
0xf0349  ldarg.2
0xf034a  ldarg.0
0xf034b  ldfld    int32 System.Windows.Media.TextFormatting.TextParagraphCache::_finiteFormatWidth
0xf0350  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xf0355  ldloca.s 3
0xf0357  ldarg.0
0xf0358  ldflda   bool System.Windows.Media.TextFormatting.TextParagraphCache::_penalizedAsJustified
0xf035d  callvirt instance valuetype MS.Internal.TextFormatting.LsErr System.Windows.Media.TextFormatting.TextFormatterContext::CreateParaBreakingSession(int32 cpFirst, int32 maxWidth, native int previousLineBreakRecord, native int& ploparabreak, bool& penalizedAsJustified)
0xf0362  stloc.1
0xf0363  ldloc.0
0xf0364  callvirt instance class [mscorlib]System.Exception System.Windows.Media.TextFormatting.TextFormatterContext::get_CallbackException()
0xf0369  stloc.2
0xf036a  ldloc.0
0xf036b  callvirt instance void System.Windows.Media.TextFormatting.TextFormatterContext::Release()
0xf0370  ldloc.1
0xf0371  brfalse.s loc_F03BB
0xf0373  ldarg.0
0xf0374  call     void [mscorlib]System.GC::SuppressFinalize(object)
0xf0379  ldloc.2
0xf037a  brfalse.s loc_F039C
0xf037c  ldstr    aCreateparabrea// "CreateParaBreakingSessionFailure"
0xf0381  ldc.i4.1
0xf0382  newarr   [mscorlib]System.Object
0xf0387  dup
0xf0388  ldc.i4.0
0xf0389  ldloc.1
0xf038a  box      MS.Internal.TextFormatting.LsErr
0xf038f  stelem.ref
0xf0390  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xf0395  ldloc.2
0xf0396  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0xf039b  throw
0xf039c  ldstr    aCreateparabrea// "CreateParaBreakingSessionFailure"
0xf03a1  ldc.i4.1
0xf03a2  newarr   [mscorlib]System.Object
0xf03a7  dup
0xf03a8  ldc.i4.0
0xf03a9  ldloc.1
0xf03aa  box      MS.Internal.TextFormatting.LsErr
0xf03af  stelem.ref
0xf03b0  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xf03b5  ldloc.1
0xf03b6  call     void System.Windows.Media.TextFormatting.TextFormatterContext::ThrowExceptionFromLsError(string message, valuetype MS.Internal.TextFormatting.LsErr lserr)
0xf03bb  ldarg.0
0xf03bc  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextParagraphCache::_ploparabreak
0xf03c1  ldloc.3
0xf03c2  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::set_Value(var<u1>)
0xf03c7  ldloc.0
0xf03c8  call     void [mscorlib]System.GC::KeepAlive(object)
0xf03cd  ret
```
