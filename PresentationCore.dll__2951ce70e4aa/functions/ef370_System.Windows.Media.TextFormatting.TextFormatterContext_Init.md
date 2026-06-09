# System.Windows.Media.TextFormatting.TextFormatterContext::Init

- ea: `0xef370`
- end: `0xef69a`
- name: `System.Windows.Media.TextFormatting.TextFormatterContext::Init`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0xef350`

## callees

- `0xef370`
- `0xef7a0`
- `0xef8d0`
- `0xef990`
- `0xef9c0`
- `0x11e170`
- `0x120ef0`
- `0x1210d0`
- `0x146e70`

## string_xrefs

- `0xef618`: `CreateContextFailure`

## pseudocode

```c

```

## disassembly

```asm
0xef370  ldarg.0
0xef371  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextFormatterContext::_ploc
0xef376  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0xef37b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xef380  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0xef385  brfalse  loc_EF699
0xef38a  ldc.i4.0
0xef38b  stloc.1
0xef38c  ldloca.s 0
0xef38e  initobj  MS.Internal.TextFormatting.LsContextInfo
0xef394  ldloca.s 6
0xef396  initobj  MS.Internal.TextFormatting.LscbkRedefined
0xef39c  ldarg.0
0xef39d  newobj   instance void MS.Internal.TextFormatting.LineServicesCallbacks::.ctor()
0xef3a2  stfld    class MS.Internal.TextFormatting.LineServicesCallbacks System.Windows.Media.TextFormatting.TextFormatterContext::_callbacks
0xef3a7  ldarg.0
0xef3a8  ldfld    class MS.Internal.TextFormatting.LineServicesCallbacks System.Windows.Media.TextFormatting.TextFormatterContext::_callbacks
0xef3ad  ldloca.s 0
0xef3af  ldloca.s 6
0xef3b1  callvirt instance void MS.Internal.TextFormatting.LineServicesCallbacks::PopulateContextInfo(valuetype MS.Internal.TextFormatting.LsContextInfo& contextInfo, valuetype MS.Internal.TextFormatting.LscbkRedefined& lscbkRedef)
0xef3b6  ldloca.s 0
0xef3b8  ldc.i4.4
0xef3b9  stfld    unsigned int32 MS.Internal.TextFormatting.LsContextInfo::version
0xef3be  ldloca.s 0
0xef3c0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xef3c5  stfld    native int MS.Internal.TextFormatting.LsContextInfo::pols
0xef3ca  ldloca.s 0
0xef3cc  ldc.i4.s 0x64
0xef3ce  stfld    int32 MS.Internal.TextFormatting.LsContextInfo::cEstimatedCharsPerLine
0xef3d3  ldloca.s 0
0xef3d5  ldc.i4.1
0xef3d6  stfld    int32 MS.Internal.TextFormatting.LsContextInfo::fDontReleaseRuns
0xef3db  ldloca.s 0
0xef3dd  ldc.i4.3
0xef3de  stfld    int32 MS.Internal.TextFormatting.LsContextInfo::cJustPriorityLim
0xef3e3  ldloca.s 0
0xef3e5  ldc.i4.0
0xef3e6  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNull
0xef3eb  ldloca.s 0
0xef3ed  ldc.i4.1
0xef3ee  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef3f3  ldloca.s 0
0xef3f5  ldc.i4.s 9
0xef3f7  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchTab
0xef3fc  ldloca.s 0
0xef3fe  ldloc.0
0xef3ff  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef404  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchPosTab
0xef409  ldloca.s 0
0xef40b  ldc.i4   0x2029
0xef410  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEndPara1
0xef415  ldloca.s 0
0xef417  ldloc.0
0xef418  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef41d  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEndPara2
0xef422  ldloca.s 0
0xef424  ldc.i4.s 0x20
0xef426  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchSpace
0xef42b  ldloca.s 0
0xef42d  ldsfld   modopt([mscorlib]System.Runtime.CompilerServices.IsConst) char MS.Internal.Text.TextInterface.TextAnalyzer::CharHyphen
0xef432  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchHyphen
0xef437  ldloca.s 0
0xef439  ldc.i4   0xAD
0xef43e  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNonReqHyphen
0xef443  ldloca.s 0
0xef445  ldc.i4   0x2011
0xef44a  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNonBreakHyphen
0xef44f  ldloca.s 0
0xef451  ldc.i4   0x2013
0xef456  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEnDash
0xef45b  ldloca.s 0
0xef45d  ldc.i4   0x2014
0xef462  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEmDash
0xef467  ldloca.s 0
0xef469  ldc.i4   0x2002
0xef46e  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEnSpace
0xef473  ldloca.s 0
0xef475  ldc.i4   0x2003
0xef47a  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEmSpace
0xef47f  ldloca.s 0
0xef481  ldc.i4   0x2009
0xef486  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNarrowSpace
0xef48b  ldloca.s 0
0xef48d  ldc.i4   0x200D
0xef492  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchJoiner
0xef497  ldloca.s 0
0xef499  ldc.i4   0x200C
0xef49e  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNonJoiner
0xef4a3  ldloca.s 0
0xef4a5  ldc.i4   0x2050
0xef4aa  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNull
0xef4af  ldloca.s 0
0xef4b1  ldc.i4   0x2051
0xef4b6  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiAltEndPara
0xef4bb  ldloca.s 0
0xef4bd  ldc.i4   0x2052
0xef4c2  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiEndLineInPara
0xef4c7  ldloca.s 0
0xef4c9  ldc.i4   0x2053
0xef4ce  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiEndPara
0xef4d3  ldloca.s 0
0xef4d5  ldc.i4   0x2054
0xef4da  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiSpace
0xef4df  ldloca.s 0
0xef4e1  ldc.i4   0x2055
0xef4e6  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNonBreakSpace
0xef4eb  ldloca.s 0
0xef4ed  ldc.i4   0x2056
0xef4f2  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNonBreakHyphen
0xef4f7  ldloca.s 0
0xef4f9  ldc.i4   0x2057
0xef4fe  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNonReqHyphen
0xef503  ldloca.s 0
0xef505  ldc.i4   0x2058
0xef50a  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiTab
0xef50f  ldloca.s 0
0xef511  ldloc.0
0xef512  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef517  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiPosTab
0xef51c  ldloca.s 0
0xef51e  ldc.i4   0x2059
0xef523  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiEmSpace
0xef528  ldloca.s 0
0xef52a  ldc.i4   0x205A
0xef52f  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiEnSpace
0xef534  ldloca.s 0
0xef536  ldc.i4   0x205B
0xef53b  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNarrowSpace
0xef540  ldloca.s 0
0xef542  ldc.i4   0x205C
0xef547  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiOptBreak
0xef54c  ldloca.s 0
0xef54e  ldc.i4   0x205D
0xef553  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiNoBreak
0xef558  ldloca.s 0
0xef55a  ldc.i4   0x205E
0xef55f  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchVisiFESpace
0xef564  ldloca.s 0
0xef566  ldc.i4   0x3000
0xef56b  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchFESpace
0xef570  ldloca.s 0
0xef572  ldc.i4   0x2029
0xef577  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEscAnmRun
0xef57c  ldloca.s 0
0xef57e  ldloc.0
0xef57f  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef584  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchAltEndPara
0xef589  ldloca.s 0
0xef58b  ldc.i4   0x2028
0xef590  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchEndLineInPara
0xef595  ldloca.s 0
0xef597  ldloc.0
0xef598  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef59d  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchSectionBreak
0xef5a2  ldloca.s 0
0xef5a4  ldc.i4   0xA0
0xef5a9  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNonBreakSpace
0xef5ae  ldloca.s 0
0xef5b0  ldloc.0
0xef5b1  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5b6  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchNoBreak
0xef5bb  ldloca.s 0
0xef5bd  ldloc.0
0xef5be  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5c3  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchColumnBreak
0xef5c8  ldloca.s 0
0xef5ca  ldloc.0
0xef5cb  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5d0  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchPageBreak
0xef5d5  ldloca.s 0
0xef5d7  ldloc.0
0xef5d8  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5dd  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchOptBreak
0xef5e2  ldloca.s 0
0xef5e4  ldloc.0
0xef5e5  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5ea  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchToReplace
0xef5ef  ldloca.s 0
0xef5f1  ldloc.0
0xef5f2  ldfld    char MS.Internal.TextFormatting.LsContextInfo::wchUndef
0xef5f7  stfld    char MS.Internal.TextFormatting.LsContextInfo::wchReplace
0xef5fc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xef601  stloc.3
0xef602  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xef607  stloc.s  5
0xef609  ldloca.s 0
0xef60b  ldloca.s 6
0xef60d  ldloca.s 3
0xef60f  call     valuetype MS.Internal.TextFormatting.LsErr MS.Internal.TextFormatting.UnsafeNativeMethods::LoCreateContext(valuetype MS.Internal.TextFormatting.LsContextInfo& contextInfo, valuetype MS.Internal.TextFormatting.LscbkRedefined& lscbkRedef, [out] native int& ploc)
0xef614  stloc.1
0xef615  ldloc.1
0xef616  brfalse.s loc_EF637
0xef618  ldstr    aCreatecontextf// "CreateContextFailure"
0xef61d  ldc.i4.1
0xef61e  newarr   [mscorlib]System.Object
0xef623  dup
0xef624  ldc.i4.0
0xef625  ldloc.1
0xef626  box      MS.Internal.TextFormatting.LsErr
0xef62b  stelem.ref
0xef62c  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xef631  ldloc.1
0xef632  call     void System.Windows.Media.TextFormatting.TextFormatterContext::ThrowExceptionFromLsError(string message, valuetype MS.Internal.TextFormatting.LsErr lserr)
0xef637  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<char, bool> System.Windows.Media.TextFormatting.TextFormatterContext::_specialCharacters
0xef63c  brtrue.s loc_EF645
0xef63e  ldloca.s 0
0xef640  call     void System.Windows.Media.TextFormatting.TextFormatterContext::SetSpecialCharacters(valuetype MS.Internal.TextFormatting.LsContextInfo& contextInfo)
0xef645  ldarg.0
0xef646  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> System.Windows.Media.TextFormatting.TextFormatterContext::_ploc
0xef64b  ldloc.3
0xef64c  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::set_Value(var<u1>)
0xef651  ldloc.0
0xef652  box      MS.Internal.TextFormatting.LsContextInfo
0xef657  call     void [mscorlib]System.GC::KeepAlive(object)
0xef65c  ldloca.s 4
0xef65e  ldloca.s 4
0xef660  ldc.i4   0x5A0
0xef665  dup
0xef666  stloc.2
0xef667  stfld    unsigned int32 MS.Internal.TextFormatting.LsDevRes::dxrInch
0xef66c  ldloc.2
0xef66d  stfld    unsigned int32 MS.Internal.TextFormatting.LsDevRes::dxpInch
0xef672  ldloca.s 4
0xef674  ldloca.s 4
0xef676  ldc.i4   0x5A0
0xef67b  dup
0xef67c  stloc.2
0xef67d  stfld    unsigned int32 MS.Internal.TextFormatting.LsDevRes::dyrInch
0xef682  ldloc.2
0xef683  stfld    unsigned int32 MS.Internal.TextFormatting.LsDevRes::dypInch
0xef688  ldarg.0
0xef689  ldc.i4.1
0xef68a  ldc.i4.1
0xef68b  ldloca.s 4
0xef68d  call     instance void System.Windows.Media.TextFormatting.TextFormatterContext::SetDoc(bool isDisplay, bool isReferencePresentationEqual, valuetype MS.Internal.TextFormatting.LsDevRes& deviceInfo)
0xef692  ldarg.0
0xef693  ldc.i4.0
0xef694  call     instance void System.Windows.Media.TextFormatting.TextFormatterContext::SetBreaking(valuetype System.Windows.Media.TextFormatting.BreakStrategies breaking)
0xef699  ret
```
