# Microsoft.Internal.GDIExporter.FontInfo::UsePrivate

- ea: `0x22cb0`
- end: `0x22d5f`
- name: `Microsoft.Internal.GDIExporter.FontInfo::UsePrivate`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ce80`

## callees

- `0x22850`
- `0x22880`
- `0x22af0`
- `0x22b10`
- `0x22b70`
- `0x22cb0`
- `0x22d60`

## string_xrefs

- `0x22d02`: `Private font should not be installed at this point`

## pseudocode

```c

```

## disassembly

```asm
0x22cb0  ldarg.1
0x22cb1  ldnull
0x22cb2  bne.un.s loc_22CB7
0x22cb4  ldc.i4.0
0x22cb5  br.s     loc_22CB8
0x22cb7  ldc.i4.1
0x22cb8  stloc.s  7
0x22cba  ldloc.s  7
0x22cbc  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x22cc1  ldarg.1
0x22cc2  newobj   instance void Microsoft.Internal.GDIExporter.FontStreamContext::.ctor(class [PresentationCore]System.Windows.Media.GlyphTypeface source)
0x22cc7  stloc.2
0x22cc8  ldarg.1
0x22cc9  call     class [System]System.Uri [ReachFramework]Microsoft.Internal.AlphaFlattener.Utility::GetFontUri(class [PresentationCore]System.Windows.Media.GlyphTypeface)
0x22cce  newobj   instance void Microsoft.Internal.GDIExporter.FontInstallInfo::.ctor(class [System]System.Uri uri)
0x22cd3  stloc.1
0x22cd4  ldarg.0
0x22cd5  ldfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22cda  stloc.s  5
0x22cdc  ldloc.s  5
0x22cde  brfalse.s loc_22CF5
0x22ce0  ldloc.1
0x22ce1  ldloc.2
0x22ce2  ldloc.s  5
0x22ce4  call     instance bool Microsoft.Internal.GDIExporter.FontInstallInfo::Equals([hasfieldmarshal] modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext value, class Microsoft.Internal.GDIExporter.FontInstallInfo context)
0x22ce9  brfalse.s loc_22CEF
0x22ceb  ldc.i4.1
0x22cec  stloc.0
0x22ced  leave.s  loc_22D5D
0x22cef  ldarg.0
0x22cf0  call     instance void Microsoft.Internal.GDIExporter.FontInfo::UninstallPrivate()
0x22cf5  ldarg.0
0x22cf6  ldfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22cfb  ldnull
0x22cfc  ceq
0x22cfe  stloc.s  6
0x22d00  ldloc.s  6
0x22d02  ldstr    aPrivateFontSho// "Private font should not be installed at"...
0x22d07  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x22d0c  ldarg.0
0x22d0d  ldfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_systemInstall
0x22d12  stloc.s  4
0x22d14  ldloc.s  4
0x22d16  brfalse.s loc_22D27
0x22d18  ldloc.1
0x22d19  ldloc.2
0x22d1a  ldloc.s  4
0x22d1c  call     instance bool Microsoft.Internal.GDIExporter.FontInstallInfo::Equals([hasfieldmarshal] modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext value, class Microsoft.Internal.GDIExporter.FontInstallInfo context)
0x22d21  brfalse.s loc_22D27
0x22d23  ldc.i4.1
0x22d24  stloc.0
0x22d25  leave.s  loc_22D5D
0x22d27  ldloc.1
0x22d28  ldloc.2
0x22d29  ldarg.0
0x22d2a  ldflda   string Microsoft.Internal.GDIExporter.FontInfo::_newFamilyName
0x22d2f  ldarg.1
0x22d30  call     instance int32 [PresentationCore]System.Windows.Media.GlyphTypeface::get_FaceIndex()
0x22d35  call     instance object Microsoft.Internal.GDIExporter.FontInstallInfo::Install(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext context, string& newFamilyName, unsigned int32 faceIndex)
0x22d3a  stloc.3
0x22d3b  ldarg.0
0x22d3c  ldloc.3
0x22d3d  stfld    object Microsoft.Internal.GDIExporter.FontInfo::_privateInstallHandle
0x22d42  ldloc.3
0x22d43  brtrue.s loc_22D49
0x22d45  ldc.i4.0
0x22d46  stloc.0
0x22d47  leave.s  loc_22D5D
0x22d49  ldarg.0
0x22d4a  ldloc.1
0x22d4b  stfld    class Microsoft.Internal.GDIExporter.FontInstallInfo Microsoft.Internal.GDIExporter.FontInfo::_privateInstall
0x22d50  ldc.i4.1
0x22d51  stloc.0
0x22d52  leave.s  loc_22D5D
0x22d54  ldloc.2
0x22d55  call     instance void Microsoft.Internal.GDIExporter.FontStreamContext::Close()
0x22d5a  endfinally
0x22d5b  ldc.i4.0
0x22d5c  ret
0x22d5d  ldloc.0
0x22d5e  ret
```
