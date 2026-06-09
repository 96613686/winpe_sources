# MS.Internal.Printing.Configuration.FallbackPTProvider::GetPrintCapabilities

- ea: `0xd8a0`
- end: `0xdb18`
- name: `MS.Internal.Printing.Configuration.FallbackPTProvider::GetPrintCapabilities`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `55`
- tags: `registry_config`

## callees

- `0xd8a0`
- `0xdc70`
- `0xddb0`
- `0xde00`
- `0xdeb0`
- `0xdfc0`
- `0x11830`
- `0x118b0`
- `0x11900`
- `0x119e0`
- `0x11a00`
- `0x11aa0`
- `0x11b00`
- `0x11b60`
- `0x11c10`
- `0x11cc0`
- `0x11d40`
- `0x11dd0`
- `0x11e50`
- `0x11f80`
- `0x120c0`
- `0x12210`
- `0x122a0`
- `0x123d0`
- `0x12520`
- `0x125a0`
- `0x12600`
- `0x14830`
- `0x148a0`
- `0x17d80`
- `0x18a20`
- `0x18de0`
- `0x18fd0`
- `0x192b0`
- `0x1a130`
- `0x1a150`
- `0x1a240`
- `0x1a250`
- `0x1a260`
- `0x1a270`
- `0x1a280`
- `0x1a290`
- `0x1a2a0`
- `0x1a2b0`
- `0x1a2d0`
- `0x1a2f0`
- `0x1a310`
- `0x1a330`
- `0x1a350`
- `0x1a370`

## string_xrefs

- `0xd8d3`: `FormatException.XMLNotWellFormed`

## pseudocode

```c

```

## disassembly

```asm
0xd8a0  ldarg.0
0xd8a1  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::VerifyAccess()
0xd8a6  ldnull
0xd8a7  stloc.0
0xd8a8  ldarg.1
0xd8a9  brtrue.s loc_D8AE
0xd8ab  ldnull
0xd8ac  br.s     loc_D8B4
0xd8ae  ldarg.1
0xd8af  newobj   instance void MS.Internal.Printing.Configuration.InternalPrintTicket::.ctor(class [mscorlib]System.IO.Stream xmlStream)
0xd8b4  stloc.0
0xd8b5  leave.s  loc_D8FA
0xd8b7  stloc.s  5
0xd8b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xd8be  ldstr    a012// "{0} {1} {2}"
0xd8c3  ldc.i4.3
0xd8c4  newarr   [mscorlib]System.Object
0xd8c9  dup
0xd8ca  ldc.i4.0
0xd8cb  ldstr    aPrintticket// "PrintTicket"
0xd8d0  stelem.ref
0xd8d1  dup
0xd8d2  ldc.i4.1
0xd8d3  ldstr    aFormatexceptio// "FormatException.XMLNotWellFormed"
0xd8d8  call     string MS.Internal.Printing.Configuration.PTUtility::GetTextFromResource(string key)
0xd8dd  stelem.ref
0xd8de  dup
0xd8df  ldc.i4.2
0xd8e0  ldloc.s  5
0xd8e2  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd8e7  stelem.ref
0xd8e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd8ed  ldstr    aPrintticket_0// "printTicket"
0xd8f2  ldloc.s  5
0xd8f4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string, class [mscorlib]System.Exception)
0xd8f9  throw
0xd8fa  ldarg.0
0xd8fb  ldc.i4.0
0xd8fc  call     instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.FallbackPTProvider::GetDEVMODE(valuetype System.Printing.Interop.BaseDevModeType baseType)
0xd901  stloc.1
0xd902  ldloc.1
0xd903  callvirt instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.DevMode::Clone()
0xd908  stloc.2
0xd909  ldarg.0
0xd90a  ldloc.2
0xd90b  ldloc.0
0xd90c  ldc.i4.2
0xd90d  ldc.i4.m1
0xd90e  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::PrintTicketToDevMode(class MS.Internal.Printing.Configuration.DevMode devMode, class MS.Internal.Printing.Configuration.InternalPrintTicket ticket, valuetype System.Printing.PrintTicketScope scope, valuetype MS.Internal.Printing.Configuration.DevModeFields supportedFields)
0xd913  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0xd918  stloc.3
0xd919  ldarg.0
0xd91a  ldloc.2
0xd91b  call     instance class MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities MS.Internal.Printing.Configuration.FallbackPTProvider::GetCapabilities(class MS.Internal.Printing.Configuration.DevMode devMode)
0xd920  stloc.s  4
0xd922  ldloc.3
0xd923  ldstr    aNs0000// "ns0000"
0xd928  ldarg.0
0xd929  call     instance string MS.Internal.Printing.Configuration.FallbackPTProvider::get_OemDriverNamespace()
0xd92e  ldc.i4.0
0xd92f  newobj   instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::.ctor(class [mscorlib]System.IO.Stream stream, string privateQname, string privateNamespace, bool indent)
0xd934  stloc.s  6
0xd936  ldloc.s  6
0xd938  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteStartDocument()
0xd93d  ldloc.s  6
0xd93f  ldloc.2
0xd940  callvirt instance unsigned int8[] MS.Internal.Printing.Configuration.DevMode::get_ByteData()
0xd945  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageDevmodeSnapshot(unsigned int8[] devMode)
0xd94a  ldloc.s  4
0xd94c  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_HasICMIntent()
0xd951  brfalse.s loc_D95A
0xd953  ldloc.s  6
0xd955  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageICMRenderingIntentFeature()
0xd95a  ldloc.s  4
0xd95c  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_HasICMMethod()
0xd961  brfalse.s loc_D96A
0xd963  ldloc.s  6
0xd965  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageColorManagementFeature()
0xd96a  ldloc.s  4
0xd96c  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_CanCollate()
0xd971  brfalse.s loc_D97A
0xd973  ldloc.s  6
0xd975  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteDocumentCollateFeature()
0xd97a  ldloc.s  4
0xd97c  callvirt instance int32 MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_MinCopies()
0xd981  stloc.s  7
0xd983  ldloc.s  4
0xd985  callvirt instance int32 MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_MaxCopies()
0xd98a  stloc.s  8
0xd98c  ldloc.s  7
0xd98e  stloc.s  9
0xd990  ldloc.s  7
0xd992  ldloc.1
0xd993  callvirt instance int16 MS.Internal.Printing.Configuration.DevMode::get_Copies()
0xd998  ldloc.s  8
0xd99a  call     int32 [mscorlib]System.Math::Min(int32, int32)
0xd99f  call     int32 [mscorlib]System.Math::Max(int32, int32)
0xd9a4  stloc.s  9
0xd9a6  ldloc.s  6
0xd9a8  ldloc.s  7
0xd9aa  ldloc.s  8
0xd9ac  ldloc.s  9
0xd9ae  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobCopiesAllDocumentsParameterDef(int32 minCopies, int32 maxCopies, int32 defaultCopies)
0xd9b3  ldloc.s  6
0xd9b5  ldloc.s  4
0xd9b7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<unsigned int32> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_NUp()
0xd9bc  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobNUpAllDocumentsContiguously(class [mscorlib]System.Collections.Generic.IList`1<unsigned int32> nUps)
0xd9c1  ldloc.s  6
0xd9c3  ldloc.s  4
0xd9c5  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_CanDuplex()
0xd9ca  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobDuplexAllDocumentsContiguouslyFeature(bool canDuplex)
0xd9cf  ldloc.s  4
0xd9d1  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_CanScale()
0xd9d6  brfalse.s loc_D9E7
0xd9d8  ldloc.s  6
0xd9da  ldc.i4.1
0xd9db  ldc.i4   0x3E8
0xd9e0  ldc.i4.s 0x64
0xd9e2  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageScalingFeature(int32 minScale, int32 maxScale, int32 defaultScale)
0xd9e7  ldloc.s  6
0xd9e9  ldloc.s  4
0xd9eb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int16> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_Papers()
0xd9f0  ldloc.s  4
0xd9f2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_PaperNames()
0xd9f7  ldloc.s  4
0xd9f9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_PAPER_SIZE> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_PaperSizes()
0xd9fe  call     class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_PAPER_SIZE> MS.Internal.Printing.Configuration.PrintSchemaShim::TenthOfMillimeterToMicrons(class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_PAPER_SIZE> points)
0xda03  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageMediaSizeFeature(class [mscorlib]System.Collections.Generic.IList`1<int16> paperSizeCodes, class [mscorlib]System.Collections.Generic.IList`1<string> paperSizeDisplayNames, class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_PAPER_SIZE> paperSizes)
0xda08  ldloc.s  6
0xda0a  ldloc.s  4
0xda0c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_RESOLUTION> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_Resolutions()
0xda11  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageResolutionFeature(class [mscorlib]System.Collections.Generic.IList`1<valuetype MS.Internal.Printing.Configuration.DC_RESOLUTION> resolutions)
0xda16  ldloc.s  4
0xda18  ldloca.s 0xA
0xda1a  ldloca.s 0xB
0xda1c  ldloca.s 0xC
0xda1e  ldloca.s 0xD
0xda20  ldloca.s 0xE
0xda22  ldloca.s 0xF
0xda24  ldloca.s 0x10
0xda26  ldloca.s 0x11
0xda28  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::TryGetDeviceCapabilities([out] int32& logicalPixelsX, [out] int32& logicalPixelsY, [out] int32& physicalWidth, [out] int32& physicalHeight, [out] int32& physicalOffsetX, [out] int32& physicalOffsetY, [out] int32& horizontalResolution, [out] int32& verticalResolution)
0xda2d  stloc.s  0x12
0xda2f  ldloc.s  0x12
0xda31  brfalse.s loc_DA92
0xda33  ldloc.s  0xA
0xda35  ldc.i4.0
0xda36  ble.s    loc_DA92
0xda38  ldloc.s  0xB
0xda3a  ldc.i4.0
0xda3b  ble.s    loc_DA92
0xda3d  ldloc.s  0xC
0xda3f  ldloc.s  0xA
0xda41  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda46  stloc.s  0x13
0xda48  ldloc.s  0xD
0xda4a  ldloc.s  0xB
0xda4c  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda51  stloc.s  0x14
0xda53  ldloc.s  0xE
0xda55  ldloc.s  0xB
0xda57  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda5c  stloc.s  0x15
0xda5e  ldloc.s  0xF
0xda60  ldloc.s  0xB
0xda62  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda67  stloc.s  0x16
0xda69  ldloc.s  0x10
0xda6b  ldloc.s  0xB
0xda6d  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda72  stloc.s  0x17
0xda74  ldloc.s  0x11
0xda76  ldloc.s  0xB
0xda78  call     int32 MS.Internal.Printing.Configuration.PrintSchemaShim::DpiToMicrons(int32 dpiLength, int32 dpi)
0xda7d  stloc.s  0x18
0xda7f  ldloc.s  6
0xda81  ldloc.s  0x13
0xda83  ldloc.s  0x14
0xda85  ldloc.s  0x15
0xda87  ldloc.s  0x16
0xda89  ldloc.s  0x17
0xda8b  ldloc.s  0x18
0xda8d  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageImageableSizeProperty(int32 imageableWidth, int32 imageableHeight, int32 originWidth, int32 originHeight, int32 extentWidth, int32 extentHeight)
0xda92  ldloc.s  6
0xda94  ldloc.s  4
0xda96  callvirt instance int32 MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_LandscapeOrientation()
0xda9b  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageOrientationFeature(int32 landscapeOrientation)
0xdaa0  ldloc.s  6
0xdaa2  ldloc.s  4
0xdaa4  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_HasColor()
0xdaa9  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageOutputColorFeature(bool supportsColor)
0xdaae  ldloc.s  6
0xdab0  ldloc.s  4
0xdab2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int16> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_Bins()
0xdab7  ldloc.s  4
0xdab9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_BinNames()
0xdabe  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobInputBinFeature(class [mscorlib]System.Collections.Generic.IList`1<int16> bins, class [mscorlib]System.Collections.Generic.IList`1<string> binDisplayNames)
0xdac3  ldloc.s  6
0xdac5  ldloc.s  4
0xdac7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<unsigned int32> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_MediaTypes()
0xdacc  ldloc.s  4
0xdace  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_MediaTypeNames()
0xdad3  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageMediaTypeFeature(class [mscorlib]System.Collections.Generic.IList`1<unsigned int32> mediaTypes, class [mscorlib]System.Collections.Generic.IList`1<string> mediaTypeDisplayNames)
0xdad8  ldloc.s  4
0xdada  callvirt instance bool MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::get_TrueType()
0xdadf  brfalse.s loc_DAEF
0xdae1  ldloc.s  6
0xdae3  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageTrueTypeFontModeFeature()
0xdae8  ldloc.s  6
0xdaea  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageDeviceFontSubstitutionFeature()
0xdaef  ldloc.s  6
0xdaf1  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteEndDocument()
0xdaf6  leave.s  loc_DB0E
0xdaf8  ldloc.s  6
0xdafa  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::Release()
0xdaff  ldnull
0xdb00  stloc.s  6
0xdb02  endfinally
0xdb03  ldloc.s  4
0xdb05  callvirt instance void MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::Release()
0xdb0a  ldnull
0xdb0b  stloc.s  4
0xdb0d  endfinally
0xdb0e  ldloc.3
0xdb0f  ldc.i4.0
0xdb10  conv.i8
0xdb11  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0xdb16  ldloc.3
0xdb17  ret
```
