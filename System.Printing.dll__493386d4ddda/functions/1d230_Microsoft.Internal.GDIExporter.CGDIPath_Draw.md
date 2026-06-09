# Microsoft.Internal.GDIExporter.CGDIPath::Draw

- ea: `0x1d230`
- end: `0x1d472`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::Draw`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1f740`

## callees

- `0x1c490`
- `0x1c4d0`
- `0x1c530`
- `0x1c5e0`
- `0x1c6d0`
- `0x1c700`
- `0x1c7a0`
- `0x1c950`
- `0x1c980`
- `0x1d230`
- `0x1d480`
- `0x1dd40`
- `0x1dd70`
- `0x1de20`

## pseudocode

```c

```

## disassembly

```asm
0x1d230  ldarg.0
0x1d231  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1d236  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d23b  ldarg.2
0x1d23c  ldnull
0x1d23d  bne.un.s loc_1D242
0x1d23f  ldc.i4.0
0x1d240  br.s     loc_1D243
0x1d242  ldc.i4.1
0x1d243  stloc.s  0xC
0x1d245  ldloc.s  0xC
0x1d247  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d24c  ldc.i4.0
0x1d24d  stloc.0
0x1d24e  ldarg.0
0x1d24f  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d254  ldc.i4.0
0x1d255  ble      loc_1D470
0x1d25a  ldarg.1
0x1d25b  ldarg.0
0x1d25c  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d261  ldloca.s 0xD
0x1d263  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype tagXFORM* oldTransform)
0x1d268  pop
0x1d269  ldarg.1
0x1d26a  ldarg.2
0x1d26b  ldc.i4.1
0x1d26c  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::SelectObject(class Microsoft.Internal.GDIExporter.GdiSafeHandle hObj, int32 type)
0x1d271  ldarg.1
0x1d272  dup
0x1d273  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_nullBrush
0x1d278  ldc.i4.2
0x1d279  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::SelectObject(class Microsoft.Internal.GDIExporter.GdiSafeHandle hObj, int32 type)
0x1d27e  ldarg.0
0x1d27f  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d284  stloc.s  5
0x1d286  ldloc.s  5
0x1d288  ldc.i4.1
0x1d289  and
0x1d28a  brfalse  loc_1D42C
0x1d28f  ldarg.0
0x1d290  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d295  stloc.s  8
0x1d297  ldloc.s  8
0x1d299  ldc.i4.1
0x1d29a  bne.un.s loc_1D2D5
0x1d29c  ldloc.s  5
0x1d29e  ldc.i4.s 0x20
0x1d2a0  and
0x1d2a1  brfalse.s loc_1D2BC
0x1d2a3  ldarg.1
0x1d2a4  ldarg.0
0x1d2a5  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d2aa  ldc.i4.0
0x1d2ab  ldarg.0
0x1d2ac  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d2b1  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d2b6  stloc.0
0x1d2b7  br       loc_1D461
0x1d2bc  ldarg.1
0x1d2bd  ldarg.0
0x1d2be  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d2c3  ldc.i4.0
0x1d2c4  ldarg.0
0x1d2c5  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d2ca  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polyline(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d2cf  stloc.0
0x1d2d0  br       loc_1D461
0x1d2d5  ldloc.s  5
0x1d2d7  ldc.i4.s 0x20
0x1d2d9  and
0x1d2da  brfalse  loc_1D415
0x1d2df  ldloc.s  5
0x1d2e1  ldc.i4.s 0x40
0x1d2e3  and
0x1d2e4  brfalse  loc_1D390
0x1d2e9  ldc.i4.0
0x1d2ea  stloc.1
0x1d2eb  ldc.i4.0
0x1d2ec  stloc.s  6
0x1d2ee  ldc.i4.0
0x1d2ef  ldloc.s  8
0x1d2f1  bge      loc_1D461
0x1d2f6  ldloc.0
0x1d2f7  ldc.i4.0
0x1d2f8  blt      loc_1D461
0x1d2fd  ldarg.0
0x1d2fe  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d303  ldloc.s  6
0x1d305  ldelem.i4
0x1d306  stloc.s  4
0x1d308  ldloc.s  4
0x1d30a  ldc.i4.0
0x1d30b  cgt
0x1d30d  stloc.s  0xB
0x1d30f  ldloc.s  0xB
0x1d311  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d316  ldloc.s  4
0x1d318  ldloc.1
0x1d319  add
0x1d31a  ldc.i4.1
0x1d31b  sub
0x1d31c  stloc.s  0xA
0x1d31e  ldarg.0
0x1d31f  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d324  stloc.2
0x1d325  ldloc.2
0x1d326  ldloc.1
0x1d327  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d32c  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d331  ldloc.2
0x1d332  ldloc.s  0xA
0x1d334  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d339  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d33e  bne.un.s loc_1D368
0x1d340  ldloc.2
0x1d341  ldloc.1
0x1d342  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d347  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d34c  ldloc.2
0x1d34d  ldloc.s  0xA
0x1d34f  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d354  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d359  bne.un.s loc_1D368
0x1d35b  ldarg.1
0x1d35c  ldloc.2
0x1d35d  ldloc.1
0x1d35e  ldloc.s  4
0x1d360  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d365  stloc.0
0x1d366  br.s     loc_1D373
0x1d368  ldarg.1
0x1d369  ldloc.2
0x1d36a  ldloc.1
0x1d36b  ldloc.s  4
0x1d36d  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polyline(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d372  stloc.0
0x1d373  ldloc.s  4
0x1d375  ldloc.1
0x1d376  add
0x1d377  stloc.1
0x1d378  ldloc.s  6
0x1d37a  ldc.i4.1
0x1d37b  add
0x1d37c  stloc.s  6
0x1d37e  ldloc.s  6
0x1d380  ldarg.0
0x1d381  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d386  blt      loc_1D2F6
0x1d38b  br       loc_1D461
0x1d390  ldarg.1
0x1d391  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIDevice::GetCaps()
0x1d396  ldc.i4.8
0x1d397  and
0x1d398  brtrue.s loc_1D3E8
0x1d39a  ldc.i4.0
0x1d39b  stloc.s  7
0x1d39d  ldc.i4.0
0x1d39e  stloc.3
0x1d39f  ldc.i4.0
0x1d3a0  ldarg.0
0x1d3a1  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d3a6  bge      loc_1D461
0x1d3ab  ldloc.0
0x1d3ac  ldc.i4.0
0x1d3ad  blt      loc_1D461
0x1d3b2  ldarg.1
0x1d3b3  ldarg.0
0x1d3b4  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d3b9  ldloc.s  7
0x1d3bb  ldarg.0
0x1d3bc  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d3c1  ldloc.3
0x1d3c2  ldelem.i4
0x1d3c3  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d3c8  stloc.0
0x1d3c9  ldloc.s  7
0x1d3cb  ldarg.0
0x1d3cc  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d3d1  ldloc.3
0x1d3d2  ldelem.i4
0x1d3d3  add
0x1d3d4  stloc.s  7
0x1d3d6  ldloc.3
0x1d3d7  ldc.i4.1
0x1d3d8  add
0x1d3d9  stloc.3
0x1d3da  ldloc.3
0x1d3db  ldarg.0
0x1d3dc  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d3e1  blt.s    loc_1D3AB
0x1d3e3  br       loc_1D461
0x1d3e8  newobj   instance void Microsoft.Internal.GDIExporter.CPolyPolygon::.ctor()
0x1d3ed  stloc.s  9
0x1d3ef  ldloc.s  9
0x1d3f1  ldarg.0
0x1d3f2  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d3f7  ldc.i4.0
0x1d3f8  ldarg.0
0x1d3f9  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d3fe  ldc.i4.0
0x1d3ff  ldarg.0
0x1d400  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d405  call     instance void Microsoft.Internal.GDIExporter.CPolyPolygon::Set(valuetype Microsoft.Internal.GDIExporter.PointI[] rgptVertex, int32 offsetP, unsigned int32[] rgcPoly, int32 offsetC, int32 cPolygons)
0x1d40a  ldloc.s  9
0x1d40c  ldarg.1
0x1d40d  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CPolyPolygon::Draw(class Microsoft.Internal.GDIExporter.CGDIDevice dc)
0x1d412  stloc.0
0x1d413  br.s     loc_1D461
0x1d415  ldarg.1
0x1d416  ldarg.0
0x1d417  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d41c  ldarg.0
0x1d41d  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d422  ldloc.s  8
0x1d424  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::PolyPolyline(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, unsigned int32[] pPolyCounts, int32 nCount)
0x1d429  stloc.0
0x1d42a  br.s     loc_1D461
0x1d42c  ldloc.s  5
0x1d42e  ldc.i4.s 0x10
0x1d430  and
0x1d431  brfalse.s loc_1D448
0x1d433  ldarg.1
0x1d434  ldarg.0
0x1d435  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d43a  ldarg.0
0x1d43b  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d440  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::PolyBezier(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 nCount)
0x1d445  stloc.0
0x1d446  br.s     loc_1D461
0x1d448  ldarg.1
0x1d449  ldarg.0
0x1d44a  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d44f  ldarg.0
0x1d450  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d455  ldarg.0
0x1d456  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d45b  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::DrawMixedPath(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, unsigned int8[] pTypes, int32 nCount)
0x1d460  stloc.0
0x1d461  ldarg.1
0x1d462  ldarg.0
0x1d463  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d468  ldloca.s 0xD
0x1d46a  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::CleanupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype tagXFORM* oldTransform)
0x1d46f  pop
0x1d470  ldloc.0
0x1d471  ret
```
