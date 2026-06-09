# MS.Internal.TextFormatting.LineServicesCallbacks::GetGlyphCompressionInfoFullMixed

- ea: `0x11fcf0`
- end: `0x11fd72`
- name: `MS.Internal.TextFormatting.LineServicesCallbacks::GetGlyphCompressionInfoFullMixed`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x11cd10`
- `0x11fcf0`
- `0x11fd80`
- `0x121280`
- `0x1212c0`
- `0x121340`
- `0x121ab0`
- `0x1276a0`

## string_xrefs

- `0x11fd59`: `GetGlyphCompressionInfoFullMixed`

## pseudocode

```c

```

## disassembly

```asm
0x11fcf0  ldc.i4.0
0x11fcf1  stloc.2
0x11fcf2  ldc.i4   0x80000000
0x11fcf7  stloc.0
0x11fcf8  ldnull
0x11fcf9  stloc.1
0x11fcfa  ldarg.s  7
0x11fcfc  ldc.i4.3
0x11fcfd  ceq
0x11fcff  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x11fd04  ldarg.s  4
0x11fd06  ldfld    valuetype MS.Internal.TextFormatting.Plsrun MS.Internal.TextFormatting.LsGlyphRunInfo::plsrun
0x11fd0b  stloc.0
0x11fd0c  ldarg.0
0x11fd0d  call     instance class MS.Internal.TextFormatting.FullTextState MS.Internal.TextFormatting.LineServicesCallbacks::get_FullText()
0x11fd12  ldloc.0
0x11fd13  callvirt instance class MS.Internal.TextFormatting.TextStore MS.Internal.TextFormatting.FullTextState::StoreFrom(valuetype MS.Internal.TextFormatting.Plsrun plsrun)
0x11fd18  ldloc.0
0x11fd19  callvirt instance class MS.Internal.TextFormatting.LSRun MS.Internal.TextFormatting.TextStore::GetRun(valuetype MS.Internal.TextFormatting.Plsrun plsrun)
0x11fd1e  stloc.1
0x11fd1f  ldloc.1
0x11fd20  callvirt instance int32 MS.Internal.TextFormatting.LSRun::get_EmSize()
0x11fd25  stloc.s  5
0x11fd27  ldarg.0
0x11fd28  ldarg.s  4
0x11fd2a  ldloc.s  5
0x11fd2c  conv.r8
0x11fd2d  ldc.r8   0.2
0x11fd36  mul
0x11fd37  conv.i4
0x11fd38  ldarg.s  8
0x11fd3a  ldarg.s  9
0x11fd3c  call     instance valuetype MS.Internal.TextFormatting.LsErr MS.Internal.TextFormatting.LineServicesCallbacks::CompressGlyphs(valuetype MS.Internal.TextFormatting.LsGlyphRunInfo* plsglyphrunInfo, int32 interWordCompressTo, int32** pplsCompressionLeft, int32** pplsCompressionRight)
0x11fd41  stloc.s  4
0x11fd43  leave.s  loc_11FD6F
0x11fd45  stloc.3
0x11fd46  ldarg.0
0x11fd47  ldloc.3
0x11fd48  ldloc.0
0x11fd49  ldloc.1
0x11fd4a  call     instance void MS.Internal.TextFormatting.LineServicesCallbacks::SaveException(class [mscorlib]System.Exception e, valuetype MS.Internal.TextFormatting.Plsrun plsrun, class MS.Internal.TextFormatting.LSRun lsrun)
0x11fd4f  ldc.i4   0xFFFE7960
0x11fd54  stloc.2
0x11fd55  leave.s  loc_11FD6D
0x11fd57  pop
0x11fd58  ldarg.0
0x11fd59  ldstr    aGetglyphcompre// "GetGlyphCompressionInfoFullMixed"
0x11fd5e  ldloc.0
0x11fd5f  ldloc.1
0x11fd60  call     instance void MS.Internal.TextFormatting.LineServicesCallbacks::SaveNonCLSException(string methodName, valuetype MS.Internal.TextFormatting.Plsrun plsrun, class MS.Internal.TextFormatting.LSRun lsrun)
0x11fd65  ldc.i4   0xFFFE7960
0x11fd6a  stloc.2
0x11fd6b  leave.s  loc_11FD6D
0x11fd6d  ldloc.2
0x11fd6e  ret
0x11fd6f  ldloc.s  4
0x11fd71  ret
```
