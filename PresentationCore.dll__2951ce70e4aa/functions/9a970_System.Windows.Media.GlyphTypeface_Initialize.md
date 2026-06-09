# System.Windows.Media.GlyphTypeface::Initialize

- ea: `0x9a970`
- end: `0x9aa69`
- name: `System.Windows.Media.GlyphTypeface::Initialize`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x9a8a0`
- `0x9bb80`

## callees

- `0xfb40`
- `0x11a00`
- `0x9a970`
- `0x9b320`
- `0x1079a0`
- `0x107a00`
- `0x12af30`
- `0x12b040`
- `0x12b9e0`
- `0x12c8a0`
- `0x12d1a0`
- `0x146e40`

## string_xrefs

- `0x9a98c`: `UriNotAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x9a970  ldarg.1
0x9a971  ldnull
0x9a972  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x9a977  brfalse.s loc_9A984
0x9a979  ldstr    aTypefacesource// "typefaceSource"
0x9a97e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9a983  throw
0x9a984  ldarg.1
0x9a985  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x9a98a  brtrue.s loc_9A9A1
0x9a98c  ldstr    aUrinotabsolute// "UriNotAbsolute"
0x9a991  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x9a996  ldstr    aTypefacesource// "typefaceSource"
0x9a99b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9a9a0  throw
0x9a9a1  ldarg.0
0x9a9a2  ldarg.1
0x9a9a3  newobj   instance void class [WindowsBase]MS.Internal.SecurityCriticalDataClass`1<class [System]System.Uri>::.ctor(var<u1>)
0x9a9a8  stfld    class [WindowsBase]MS.Internal.SecurityCriticalDataClass`1<class [System]System.Uri> System.Windows.Media.GlyphTypeface::_originalUri
0x9a9ad  ldarg.1
0x9a9ae  ldloca.s 1
0x9a9b0  ldloca.s 3
0x9a9b2  call     void MS.Internal.FontCache.Util::SplitFontFaceIndex(class [System]System.Uri fontUri, [out] class [System]System.Uri& fontSourceUri, [out] int32& faceIndex)
0x9a9b7  ldarg.0
0x9a9b8  ldloc.1
0x9a9b9  call     class [mscorlib]System.Security.CodeAccessPermission MS.Internal.SecurityHelper::CreateUriReadPermission(class [System]System.Uri uri)
0x9a9be  newobj   instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [mscorlib]System.Security.CodeAccessPermission>::.ctor(var<u1>)
0x9a9c3  stfld    valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class [mscorlib]System.Security.CodeAccessPermission> System.Windows.Media.GlyphTypeface::_fileIOPermObj
0x9a9c8  ldarg.0
0x9a9c9  call     instance void System.Windows.Media.GlyphTypeface::DemandPermissionsForFontInformation()
0x9a9ce  ldarg.2
0x9a9cf  brfalse.s loc_9A9F3
0x9a9d1  ldarg.2
0x9a9d2  ldc.i4.2
0x9a9d3  beq.s    loc_9A9F3
0x9a9d5  ldarg.2
0x9a9d6  ldc.i4.1
0x9a9d7  beq.s    loc_9A9F3
0x9a9d9  ldarg.2
0x9a9da  ldc.i4.3
0x9a9db  beq.s    loc_9A9F3
0x9a9dd  ldstr    aStylesimulatio// "styleSimulations"
0x9a9e2  ldarg.2
0x9a9e3  ldtoken  System.Windows.Media.StyleSimulations
0x9a9e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a9ed  newobj   instance void [System]System.ComponentModel.InvalidEnumArgumentException::.ctor(string, int32, class [mscorlib]System.Type)
0x9a9f2  throw
0x9a9f3  ldarg.0
0x9a9f4  ldarg.2
0x9a9f5  stfld    valuetype System.Windows.Media.StyleSimulations System.Windows.Media.GlyphTypeface::_styleSimulations
0x9a9fa  ldloc.1
0x9a9fb  call     class MS.Internal.Text.TextInterface.FontCollection MS.Internal.FontCache.DWriteFactory::GetFontCollectionFromFile(class [System]System.Uri fontCollectionUri)
0x9aa00  stloc.2
0x9aa01  call     class MS.Internal.Text.TextInterface.Factory MS.Internal.FontCache.DWriteFactory::get_Instance()
0x9aa06  ldloc.1
0x9aa07  ldloc.3
0x9aa08  ldarg.2
0x9aa09  callvirt instance class MS.Internal.Text.TextInterface.FontFace MS.Internal.Text.TextInterface.Factory::CreateFontFace(class [System]System.Uri filePathUri, unsigned int32 faceIndex, valuetype MS.Internal.Text.TextInterface.FontSimulations fontSimulationFlags)
0x9aa0e  stloc.0
0x9aa0f  ldloc.0
0x9aa10  brtrue.s loc_9AA2A
0x9aa12  ldarg.1
0x9aa13  call     void MS.Internal.SecurityHelper::DemandUriDiscoveryPermission(class [System]System.Uri uri)
0x9aa18  ldarg.1
0x9aa19  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(class [System]System.Uri)
0x9aa1e  throw
0x9aa1f  leave.s  loc_9AA2A
0x9aa21  pop
0x9aa22  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor()
0x9aa27  throw
0x9aa28  leave.s  loc_9AA2A
0x9aa2a  ldarg.0
0x9aa2b  ldloc.2
0x9aa2c  ldloc.0
0x9aa2d  callvirt instance class MS.Internal.Text.TextInterface.Font MS.Internal.Text.TextInterface.FontCollection::GetFontFromFontFace(class MS.Internal.Text.TextInterface.FontFace fontFace)
0x9aa32  stfld    class MS.Internal.Text.TextInterface.Font System.Windows.Media.GlyphTypeface::_font
0x9aa37  leave.s  loc_9AA43
0x9aa39  ldloc.0
0x9aa3a  brfalse.s loc_9AA42
0x9aa3c  ldloc.0
0x9aa3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9aa42  endfinally
0x9aa43  ldarg.0
0x9aa44  ldarg.0
0x9aa45  ldfld    class MS.Internal.Text.TextInterface.Font System.Windows.Media.GlyphTypeface::_font
0x9aa4a  newobj   instance void MS.Internal.FontCache.FontFaceLayoutInfo::.ctor(class MS.Internal.Text.TextInterface.Font font)
0x9aa4f  stfld    class MS.Internal.FontCache.FontFaceLayoutInfo System.Windows.Media.GlyphTypeface::_fontFace
0x9aa54  ldarg.0
0x9aa55  ldloc.1
0x9aa56  ldc.i4.1
0x9aa57  newobj   instance void MS.Internal.FontCache.FontSource::.ctor(class [System]System.Uri fontUri, bool skipDemand)
0x9aa5c  stfld    class MS.Internal.FontCache.FontSource System.Windows.Media.GlyphTypeface::_fontSource
0x9aa61  ldarg.0
0x9aa62  ldc.i4.2
0x9aa63  stfld    valuetype InitializationState System.Windows.Media.GlyphTypeface::_initializationState
0x9aa68  ret
```
