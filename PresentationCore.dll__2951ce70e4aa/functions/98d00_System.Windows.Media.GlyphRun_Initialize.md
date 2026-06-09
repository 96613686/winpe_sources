# System.Windows.Media.GlyphRun::Initialize

- ea: `0x98d00`
- end: `0x990fc`
- name: `System.Windows.Media.GlyphRun::Initialize`
- size: `1020`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x98c10`
- `0x98c60`
- `0x98cb0`
- `0x9a680`

## callees

- `0x98d00`
- `0x99960`
- `0x99970`
- `0x9a7f0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x98f9c`: `SidewaysRTLTextIsNotSupported`
- `0x98fb5`: `renderingEmSize`
- `0x98fd7`: `renderingEmSize`

## pseudocode

```c

```

## disassembly

```asm
0x98d00  ldarg.1
0x98d01  brfalse  loc_98FAC
0x98d06  ldarg.s  6
0x98d08  brfalse  loc_98FAC
0x98d0d  ldarg.s  8
0x98d0f  brfalse  loc_98FAC
0x98d14  ldarg.s  4
0x98d16  ldc.r8   0.0
0x98d1f  blt.un   loc_98FAC
0x98d24  ldarg.s  6
0x98d26  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98d2b  ldc.i4.0
0x98d2c  ble      loc_98FAC
0x98d31  ldarg.s  6
0x98d33  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98d38  ldc.i4   0xFFFF
0x98d3d  bgt      loc_98FAC
0x98d42  ldarg.s  8
0x98d44  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<float64>::get_Count()
0x98d49  ldarg.s  6
0x98d4b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98d50  bne.un   loc_98FAC
0x98d55  ldarg.s  9
0x98d57  brfalse.s loc_98D7F
0x98d59  ldarg.s  9
0x98d5b  brfalse  loc_98FAC
0x98d60  ldarg.s  9
0x98d62  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [WindowsBase]System.Windows.Point>::get_Count()
0x98d67  brfalse  loc_98FAC
0x98d6c  ldarg.s  9
0x98d6e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [WindowsBase]System.Windows.Point>::get_Count()
0x98d73  ldarg.s  6
0x98d75  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98d7a  bne.un   loc_98FAC
0x98d7f  ldarg.0
0x98d80  ldarg.s  0xF
0x98d82  stfld    valuetype System.Windows.Media.TextFormattingMode System.Windows.Media.GlyphRun::_textFormattingMode
0x98d87  ldarg.0
0x98d88  ldarg.s  6
0x98d8a  stfld    class [mscorlib]System.Collections.Generic.IList`1<unsigned int16> System.Windows.Media.GlyphRun::_glyphIndices
0x98d8f  ldarg.0
0x98d90  ldarg.s  0xA
0x98d92  stfld    class [mscorlib]System.Collections.Generic.IList`1<char> System.Windows.Media.GlyphRun::_characters
0x98d97  ldarg.0
0x98d98  ldarg.s  0xC
0x98d9a  stfld    class [mscorlib]System.Collections.Generic.IList`1<unsigned int16> System.Windows.Media.GlyphRun::_clusterMap
0x98d9f  ldarg.0
0x98da0  ldarg.s  7
0x98da2  stfld    valuetype [WindowsBase]System.Windows.Point System.Windows.Media.GlyphRun::_baselineOrigin
0x98da7  ldarg.0
0x98da8  ldarg.s  4
0x98daa  stfld    float64 System.Windows.Media.GlyphRun::_renderingEmSize
0x98daf  ldarg.0
0x98db0  ldarg.s  8
0x98db2  stfld    class [mscorlib]System.Collections.Generic.IList`1<float64> System.Windows.Media.GlyphRun::_advanceWidths
0x98db7  ldarg.0
0x98db8  ldarg.s  9
0x98dba  stfld    class [mscorlib]System.Collections.Generic.IList`1<valuetype [WindowsBase]System.Windows.Point> System.Windows.Media.GlyphRun::_glyphOffsets
0x98dbf  ldarg.0
0x98dc0  ldarg.1
0x98dc1  stfld    class System.Windows.Media.GlyphTypeface System.Windows.Media.GlyphRun::_glyphTypeface
0x98dc6  ldarg.0
0x98dc7  ldarg.3
0x98dc8  brtrue.s loc_98DCD
0x98dca  ldc.i4.0
0x98dcb  br.s     loc_98DCE
0x98dcd  ldc.i4.1
0x98dce  stfld    valuetype GlyphRunFlags System.Windows.Media.GlyphRun::_flags
0x98dd3  ldarg.0
0x98dd4  ldarg.2
0x98dd5  stfld    int32 System.Windows.Media.GlyphRun::_bidiLevel
0x98dda  ldarg.0
0x98ddb  ldarg.s  0xD
0x98ddd  stfld    class [mscorlib]System.Collections.Generic.IList`1<bool> System.Windows.Media.GlyphRun::_caretStops
0x98de2  ldarg.0
0x98de3  ldarg.s  0xE
0x98de5  stfld    class System.Windows.Markup.XmlLanguage System.Windows.Media.GlyphRun::_language
0x98dea  ldarg.0
0x98deb  ldarg.s  0xB
0x98ded  stfld    string System.Windows.Media.GlyphRun::_deviceFontName
0x98df2  ldarg.0
0x98df3  ldarg.s  5
0x98df5  stfld    float32 System.Windows.Media.GlyphRun::_pixelsPerDip
0x98dfa  ldarg.s  0xA
0x98dfc  brfalse  loc_98F45
0x98e01  ldarg.s  0xA
0x98e03  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<char>::get_Count()
0x98e08  brfalse  loc_98F45
0x98e0d  ldarg.s  0xC
0x98e0f  brfalse  loc_98F0D
0x98e14  ldarg.s  0xC
0x98e16  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98e1b  brfalse  loc_98F0D
0x98e20  ldarg.s  0xC
0x98e22  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98e27  ldarg.s  0xA
0x98e29  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<char>::get_Count()
0x98e2e  bne.un   loc_98EE3
0x98e33  ldarg.s  0xC
0x98e35  ldc.i4.0
0x98e36  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98e3b  brtrue   loc_98ECE
0x98e40  ldarg.0
0x98e41  call     instance int32 System.Windows.Media.GlyphRun::get_GlyphCount()
0x98e46  stloc.s  4
0x98e48  ldarg.s  0xC
0x98e4a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x98e4f  stloc.3
0x98e50  ldarg.s  0xC
0x98e52  ldc.i4.0
0x98e53  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98e58  stloc.2
0x98e59  ldc.i4.1
0x98e5a  stloc.0
0x98e5b  br.s     loc_98EC5
0x98e5d  ldarg.s  0xC
0x98e5f  ldloc.0
0x98e60  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98e65  stloc.1
0x98e66  ldloc.1
0x98e67  ldloc.2
0x98e68  blt.s    loc_98E73
0x98e6a  ldloc.1
0x98e6b  ldloc.s  4
0x98e6d  bge.s    loc_98E73
0x98e6f  ldloc.1
0x98e70  stloc.2
0x98e71  br.s     loc_98EC1
0x98e73  ldarg.s  0xC
0x98e75  ldloc.0
0x98e76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98e7b  ldarg.s  0xC
0x98e7d  ldloc.0
0x98e7e  ldc.i4.1
0x98e7f  sub
0x98e80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98e85  bge.s    loc_98E9C
0x98e87  ldstr    aClustermapentr// "ClusterMapEntriesShouldNotDecrease"
0x98e8c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98e91  ldstr    aClustermap// "clusterMap"
0x98e96  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98e9b  throw
0x98e9c  ldarg.s  0xC
0x98e9e  ldloc.0
0x98e9f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<unsigned int16>::get_Item(!!T0)
0x98ea4  ldarg.0
0x98ea5  call     instance int32 System.Windows.Media.GlyphRun::get_GlyphCount()
0x98eaa  blt.s    loc_98EC1
0x98eac  ldstr    aClustermapentr_0// "ClusterMapEntryShouldPointWithinGlyphIn"...
0x98eb1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98eb6  ldstr    aClustermap// "clusterMap"
0x98ebb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98ec0  throw
0x98ec1  ldloc.0
0x98ec2  ldc.i4.1
0x98ec3  add
0x98ec4  stloc.0
0x98ec5  ldloc.0
0x98ec6  ldloc.3
0x98ec7  blt.s    loc_98E5D
0x98ec9  br       loc_98F45
0x98ece  ldstr    aClustermapfirs// "ClusterMapFirstEntryMustBeZero"
0x98ed3  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98ed8  ldstr    aClustermap// "clusterMap"
0x98edd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98ee2  throw
0x98ee3  ldstr    aCollectionnumb// "CollectionNumberOfElementsShouldBeEqual"...
0x98ee8  ldc.i4.1
0x98ee9  newarr   [mscorlib]System.Object
0x98eee  dup
0x98eef  ldc.i4.0
0x98ef0  ldarg.s  0xA
0x98ef2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<char>::get_Count()
0x98ef7  box      [mscorlib]System.Int32
0x98efc  stelem.ref
0x98efd  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x98f02  ldstr    aClustermap// "clusterMap"
0x98f07  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98f0c  throw
0x98f0d  ldarg.0
0x98f0e  call     instance int32 System.Windows.Media.GlyphRun::get_GlyphCount()
0x98f13  ldarg.s  0xA
0x98f15  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<char>::get_Count()
0x98f1a  beq.s    loc_98F45
0x98f1c  ldstr    aCollectionnumb// "CollectionNumberOfElementsShouldBeEqual"...
0x98f21  ldc.i4.1
0x98f22  newarr   [mscorlib]System.Object
0x98f27  dup
0x98f28  ldc.i4.0
0x98f29  ldarg.0
0x98f2a  call     instance int32 System.Windows.Media.GlyphRun::get_GlyphCount()
0x98f2f  box      [mscorlib]System.Int32
0x98f34  stelem.ref
0x98f35  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x98f3a  ldstr    aClustermap// "clusterMap"
0x98f3f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98f44  throw
0x98f45  ldarg.s  0xD
0x98f47  brfalse.s loc_98F8E
0x98f49  ldarg.s  0xD
0x98f4b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<bool>::get_Count()
0x98f50  brfalse.s loc_98F8E
0x98f52  ldarg.s  0xD
0x98f54  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<bool>::get_Count()
0x98f59  ldarg.0
0x98f5a  call     instance int32 System.Windows.Media.GlyphRun::get_CodepointCount()
0x98f5f  ldc.i4.1
0x98f60  add
0x98f61  beq.s    loc_98F8E
0x98f63  ldstr    aCollectionnumb// "CollectionNumberOfElementsShouldBeEqual"...
0x98f68  ldc.i4.1
0x98f69  newarr   [mscorlib]System.Object
0x98f6e  dup
0x98f6f  ldc.i4.0
0x98f70  ldarg.0
0x98f71  call     instance int32 System.Windows.Media.GlyphRun::get_CodepointCount()
0x98f76  ldc.i4.1
0x98f77  add
0x98f78  box      [mscorlib]System.Int32
0x98f7d  stelem.ref
0x98f7e  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x98f83  ldstr    aCaretstops// "caretStops"
0x98f88  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x98f8d  throw
0x98f8e  ldarg.3
0x98f8f  brfalse  loc_990F4
0x98f94  ldarg.2
0x98f95  ldc.i4.1
0x98f96  and
0x98f97  brfalse  loc_990F4
0x98f9c  ldstr    aSidewaysrtltex// "SidewaysRTLTextIsNotSupported"
0x98fa1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98fa6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x98fab  throw
0x98fac  ldarg.s  4
0x98fae  call     bool [WindowsBase]MS.Internal.DoubleUtil::IsNaN(float64)
0x98fb3  brfalse.s loc_98FCA
0x98fb5  ldstr    aRenderingemsiz// "renderingEmSize"
0x98fba  ldstr    aParametervalue// "ParameterValueCannotBeNaN"
0x98fbf  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98fc4  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x98fc9  throw
0x98fca  ldarg.s  4
0x98fcc  ldc.r8   0.0
0x98fd5  bge.un.s loc_98FEC
0x98fd7  ldstr    aRenderingemsiz// "renderingEmSize"
0x98fdc  ldstr    aParametervalue_0// "ParameterValueCannotBeNegative"
0x98fe1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x98fe6  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x98feb  throw
0x98fec  ldarg.1
0x98fed  brtrue.s loc_98FFA
0x98fef  ldstr    aGlyphtypeface// "glyphTypeface"
0x98ff4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x98ff9  throw
0x98ffa  ldarg.s  6
0x98ffc  brtrue.s loc_99009
0x98ffe  ldstr    aGlyphindices// "glyphIndices"
0x99003  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x99008  throw
0x99009  ldarg.s  6
0x9900b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x99010  ldc.i4.0
0x99011  bgt.s    loc_99028
0x99013  ldstr    aCollectionnumb_0// "CollectionNumberOfElementsMustBeGreater"...
0x99018  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x9901d  ldstr    aGlyphindices// "glyphIndices"
0x99022  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x99027  throw
0x99028  ldarg.s  6
0x9902a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x9902f  ldc.i4   0xFFFF
0x99034  ble.s    loc_9905E
0x99036  ldstr    aCollectionnumb_1// "CollectionNumberOfElementsMustBeLessOrE"...
0x9903b  ldc.i4.1
0x9903c  newarr   [mscorlib]System.Object
0x99041  dup
0x99042  ldc.i4.0
0x99043  ldc.i4   0xFFFF
0x99048  box      [mscorlib]System.Int32
0x9904d  stelem.ref
0x9904e  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x99053  ldstr    aGlyphindices// "glyphIndices"
0x99058  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9905d  throw
0x9905e  ldarg.s  8
0x99060  brtrue.s loc_9906D
0x99062  ldstr    aAdvancewidths// "advanceWidths"
0x99067  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9906c  throw
0x9906d  ldarg.s  8
0x9906f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<float64>::get_Count()
0x99074  ldarg.s  6
0x99076  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<unsigned int16>::get_Count()
0x9907b  beq.s    loc_990A7
0x9907d  ldstr    aCollectionnumb// "CollectionNumberOfElementsShouldBeEqual"...
0x99082  ldc.i4.1
0x99083  newarr   [mscorlib]System.Object
0x99088  dup
0x99089  ldc.i4.0
  ... truncated ...
```
