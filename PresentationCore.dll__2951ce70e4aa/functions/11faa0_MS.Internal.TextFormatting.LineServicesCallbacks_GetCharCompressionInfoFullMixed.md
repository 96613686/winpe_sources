# MS.Internal.TextFormatting.LineServicesCallbacks::GetCharCompressionInfoFullMixed

- ea: `0x11faa0`
- end: `0x11fb1f`
- name: `MS.Internal.TextFormatting.LineServicesCallbacks::GetCharCompressionInfoFullMixed`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x11cd10`
- `0x11faa0`
- `0x11fba0`
- `0x121280`
- `0x1212c0`
- `0x121340`
- `0x121ab0`
- `0x1276a0`

## string_xrefs

- `0x11fb06`: `GetCharCompressionInfoFullMixed`

## pseudocode

```c

```

## disassembly

```asm
0x11faa0  ldc.i4.0
0x11faa1  stloc.2
0x11faa2  ldc.i4   0x80000000
0x11faa7  stloc.0
0x11faa8  ldnull
0x11faa9  stloc.1
0x11faaa  ldarg.s  7
0x11faac  ldc.i4.3
0x11faad  ceq
0x11faaf  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11fab4  ldarg.s  4
0x11fab6  ldfld    valuetype MS.Internal.TextFormatting.Plsrun MS.Internal.TextFormatting.LsCharRunInfo::plsrun
0x11fabb  stloc.0
0x11fabc  ldarg.0
0x11fabd  call     instance class MS.Internal.TextFormatting.FullTextState MS.Internal.TextFormatting.LineServicesCallbacks::get_FullText()
0x11fac2  ldloc.0
0x11fac3  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::StoreFrom(valuetype MS.Internal.TextFormatting.Plsrun plsrun)
0x11fac8  ldloc.0
0x11fac9  callvirt instance class MS.Internal.TextFormatting.LSRun MS.Internal.TextFormatting.TextStore::GetRun(valuetype MS.Internal.TextFormatting.Plsrun plsrun)
0x11face  stloc.1
0x11facf  ldarg.0
0x11fad0  ldarg.s  4
0x11fad2  ldc.i4.0
0x11fad3  ldloc.1
0x11fad4  callvirt instance int32 MS.Internal.TextFormatting.LSRun::get_EmSize()
0x11fad9  conv.r8
0x11fada  ldc.r8   0.2
0x11fae3  mul
0x11fae4  conv.i4
0x11fae5  ldarg.s  8
0x11fae7  ldarg.s  9
0x11fae9  call     instance valuetype MS.Internal.TextFormatting.LsErr MS.Internal.TextFormatting.LineServicesCallbacks::AdjustChars(valuetype MS.Internal.TextFormatting.LsCharRunInfo* plscharrunInfo, bool expanding, int32 interWordAdjustTo, int32** pplsAdjustLeft, int32** pplsAdjustRight)
0x11faee  stloc.s  4
0x11faf0  leave.s  loc_11FB1C
0x11faf2  stloc.3
0x11faf3  ldarg.0
0x11faf4  ldloc.3
0x11faf5  ldloc.0
0x11faf6  ldloc.1
0x11faf7  call     instance void MS.Internal.TextFormatting.LineServicesCallbacks::SaveException(class [mscorlib]System.Exception e, valuetype MS.Internal.TextFormatting.Plsrun plsrun, class MS.Internal.TextFormatting.LSRun lsrun)
0x11fafc  ldc.i4   0xFFFE7960
0x11fb01  stloc.2
0x11fb02  leave.s  loc_11FB1A
0x11fb04  pop
0x11fb05  ldarg.0
0x11fb06  ldstr    aGetcharcompres// "GetCharCompressionInfoFullMixed"
0x11fb0b  ldloc.0
0x11fb0c  ldloc.1
0x11fb0d  call     instance void MS.Internal.TextFormatting.LineServicesCallbacks::SaveNonCLSException(string methodName, valuetype MS.Internal.TextFormatting.Plsrun plsrun, class MS.Internal.TextFormatting.LSRun lsrun)
0x11fb12  ldc.i4   0xFFFE7960
0x11fb17  stloc.2
0x11fb18  leave.s  loc_11FB1A
0x11fb1a  ldloc.2
0x11fb1b  ret
0x11fb1c  ldloc.s  4
0x11fb1e  ret
```
