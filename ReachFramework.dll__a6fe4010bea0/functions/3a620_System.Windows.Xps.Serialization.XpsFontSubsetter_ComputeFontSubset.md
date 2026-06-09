# System.Windows.Xps.Serialization.XpsFontSubsetter::ComputeFontSubset

- ea: `0x3a620`
- end: `0x3a6ba`
- name: `System.Windows.Xps.Serialization.XpsFontSubsetter::ComputeFontSubset`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x3ae80`

## callees

- `0x1fec0`
- `0x2e7f0`
- `0x2e9d0`
- `0x3a620`
- `0x3a820`
- `0x3a920`
- `0x3aa40`
- `0x3ac50`
- `0x3add0`
- `0x3adf0`

## pseudocode

```c

```

## disassembly

```asm
0x3a620  ldc.i4.4
0x3a621  stloc.0
0x3a622  ldarg.1
0x3a623  brtrue.s loc_3A630
0x3a625  ldstr    aGlyphrun// "glyphRun"
0x3a62a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3a62f  throw
0x3a630  ldnull
0x3a631  stloc.1
0x3a632  ldarg.1
0x3a633  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x3a638  callvirt instance class [mscorlib]System.Security.CodeAccessPermission [PresentationCore]System.Windows.Media.GlyphTypeface::get_CriticalFileReadPermission()
0x3a63d  stloc.2
0x3a63e  ldloc.2
0x3a63f  brfalse.s loc_3A647
0x3a641  ldloc.2
0x3a642  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x3a647  nop
0x3a648  ldarg.1
0x3a649  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x3a64e  callvirt instance valuetype [PresentationCore]System.Windows.Media.FontEmbeddingRight [PresentationCore]System.Windows.Media.GlyphTypeface::get_EmbeddingRights()
0x3a653  stloc.0
0x3a654  leave.s  loc_3A65F
0x3a656  ldloc.2
0x3a657  brfalse.s loc_3A65E
0x3a659  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x3a65e  endfinally
0x3a65f  ldloc.0
0x3a660  call     valuetype System.Windows.Xps.Serialization.FontEmbeddingAction System.Windows.Xps.Serialization.XpsFontSubsetter::DetermineEmbeddingAction(valuetype [PresentationCore]System.Windows.Media.FontEmbeddingRight fsType)
0x3a665  ldc.i4.4
0x3a666  bne.un.s loc_3A680
0x3a668  ldarg.0
0x3a669  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsFontSubsetter::_packagingPolicy
0x3a66e  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ImageUriPlaceHolder()
0x3a673  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.BasePackagingPolicy::AcquireResourceStreamForXpsImage(string resourceId)
0x3a678  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.XpsResourceStream::get_Uri()
0x3a67d  stloc.1
0x3a67e  br.s     loc_3A6B8
0x3a680  ldarg.0
0x3a681  ldarg.1
0x3a682  callvirt instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x3a687  call     instance class System.Windows.Xps.Serialization.FEMCacheItem System.Windows.Xps.Serialization.XpsFontSubsetter::AcquireCacheItem(class [PresentationCore]System.Windows.Media.GlyphTypeface glyphTypeface)
0x3a68c  stloc.3
0x3a68d  ldloc.3
0x3a68e  brfalse.s loc_3A6B8
0x3a690  ldloc.3
0x3a691  ldc.i4.1
0x3a692  callvirt instance void System.Windows.Xps.Serialization.FEMCacheItem::set_CurrentPageReferences(bool value)
0x3a697  ldarg.0
0x3a698  ldfld    valuetype System.Windows.Xps.Serialization.FontSubsetterCommitPolicies System.Windows.Xps.Serialization.XpsFontSubsetter::_commitPolicy
0x3a69d  brtrue.s loc_3A6B0
0x3a69f  ldloc.3
0x3a6a0  callvirt instance bool System.Windows.Xps.Serialization.FEMCacheItem::get_IsStreamWritten()
0x3a6a5  brtrue.s loc_3A6B0
0x3a6a7  ldloc.3
0x3a6a8  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.FEMCacheItem::CopyFontStream()
0x3a6ad  stloc.1
0x3a6ae  br.s     loc_3A6B8
0x3a6b0  ldloc.3
0x3a6b1  ldarg.1
0x3a6b2  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.FEMCacheItem::AddGlyphRunUsage(class [PresentationCore]System.Windows.Media.GlyphRun glyphRun)
0x3a6b7  stloc.1
0x3a6b8  ldloc.1
0x3a6b9  ret
```
