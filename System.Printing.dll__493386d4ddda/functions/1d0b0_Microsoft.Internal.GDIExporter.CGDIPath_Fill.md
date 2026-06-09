# Microsoft.Internal.GDIExporter.CGDIPath::Fill

- ea: `0x1d0b0`
- end: `0x1d223`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::Fill`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1f8d0`

## callees

- `0x1c490`
- `0x1c4d0`
- `0x1c530`
- `0x1c5e0`
- `0x1c620`
- `0x1c6d0`
- `0x1c7d0`
- `0x1c7f0`
- `0x1c810`
- `0x1c950`
- `0x1c980`
- `0x1d0b0`
- `0x1d480`
- `0x1dd40`
- `0x1dd70`
- `0x1de20`

## pseudocode

```c

```

## disassembly

```asm
0x1d0b0  ldarg.0
0x1d0b1  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1d0b6  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d0bb  ldarg.2
0x1d0bc  ldnull
0x1d0bd  bne.un.s loc_1D0C2
0x1d0bf  ldc.i4.0
0x1d0c0  br.s     loc_1D0C3
0x1d0c2  ldc.i4.1
0x1d0c3  stloc.s  4
0x1d0c5  ldloc.s  4
0x1d0c7  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d0cc  ldc.i4.0
0x1d0cd  stloc.0
0x1d0ce  ldarg.0
0x1d0cf  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d0d4  ldc.i4.0
0x1d0d5  ble      loc_1D221
0x1d0da  ldarg.1
0x1d0db  ldarg.0
0x1d0dc  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d0e1  ldloca.s 5
0x1d0e3  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype tagXFORM* oldTransform)
0x1d0e8  pop
0x1d0e9  ldarg.1
0x1d0ea  ldarg.2
0x1d0eb  ldc.i4.2
0x1d0ec  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::SelectObject(class Microsoft.Internal.GDIExporter.GdiSafeHandle hObj, int32 type)
0x1d0f1  ldarg.1
0x1d0f2  ldarg.0
0x1d0f3  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_PathFillMode
0x1d0f8  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetPolyFillMode(int32 polyfillmode)
0x1d0fd  pop
0x1d0fe  ldarg.0
0x1d0ff  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d104  ldc.i4.1
0x1d105  and
0x1d106  brfalse  loc_1D1B8
0x1d10b  ldarg.1
0x1d10c  dup
0x1d10d  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_nullPen
0x1d112  ldc.i4.1
0x1d113  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::SelectObject(class Microsoft.Internal.GDIExporter.GdiSafeHandle hObj, int32 type)
0x1d118  ldarg.0
0x1d119  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d11e  ldc.i4.1
0x1d11f  bne.un.s loc_1D13A
0x1d121  ldarg.1
0x1d122  ldarg.0
0x1d123  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d128  ldc.i4.0
0x1d129  ldarg.0
0x1d12a  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d12f  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d134  stloc.0
0x1d135  br       loc_1D212
0x1d13a  ldarg.1
0x1d13b  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIDevice::GetCaps()
0x1d140  ldc.i4.8
0x1d141  and
0x1d142  brtrue.s loc_1D18E
0x1d144  ldc.i4.0
0x1d145  stloc.2
0x1d146  ldc.i4.0
0x1d147  stloc.1
0x1d148  ldc.i4.0
0x1d149  ldarg.0
0x1d14a  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d14f  bge      loc_1D212
0x1d154  ldloc.0
0x1d155  ldc.i4.0
0x1d156  blt      loc_1D212
0x1d15b  ldarg.1
0x1d15c  ldarg.0
0x1d15d  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d162  ldloc.2
0x1d163  ldarg.0
0x1d164  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d169  ldloc.1
0x1d16a  ldelem.i4
0x1d16b  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d170  stloc.0
0x1d171  ldloc.2
0x1d172  ldarg.0
0x1d173  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d178  ldloc.1
0x1d179  ldelem.i4
0x1d17a  add
0x1d17b  stloc.2
0x1d17c  ldloc.1
0x1d17d  ldc.i4.1
0x1d17e  add
0x1d17f  stloc.1
0x1d180  ldloc.1
0x1d181  ldarg.0
0x1d182  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d187  blt.s    loc_1D154
0x1d189  br       loc_1D212
0x1d18e  newobj   instance void Microsoft.Internal.GDIExporter.CPolyPolygon::.ctor()
0x1d193  stloc.3
0x1d194  ldloc.3
0x1d195  ldarg.0
0x1d196  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d19b  ldc.i4.0
0x1d19c  ldarg.0
0x1d19d  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d1a2  ldc.i4.0
0x1d1a3  ldarg.0
0x1d1a4  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d1a9  call     instance void Microsoft.Internal.GDIExporter.CPolyPolygon::Set(valuetype Microsoft.Internal.GDIExporter.PointI[] rgptVertex, int32 offsetP, unsigned int32[] rgcPoly, int32 offsetC, int32 cPolygons)
0x1d1ae  ldloc.3
0x1d1af  ldarg.1
0x1d1b0  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CPolyPolygon::Draw(class Microsoft.Internal.GDIExporter.CGDIDevice dc)
0x1d1b5  stloc.0
0x1d1b6  br.s     loc_1D212
0x1d1b8  ldarg.1
0x1d1b9  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::BeginPath()
0x1d1be  stloc.0
0x1d1bf  ldloc.0
0x1d1c0  ldc.i4.0
0x1d1c1  blt.s    loc_1D212
0x1d1c3  ldarg.0
0x1d1c4  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d1c9  ldc.i4.s 0x10
0x1d1cb  and
0x1d1cc  brfalse.s loc_1D1E3
0x1d1ce  ldarg.1
0x1d1cf  ldarg.0
0x1d1d0  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d1d5  ldarg.0
0x1d1d6  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d1db  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::PolyBezier(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 nCount)
0x1d1e0  stloc.0
0x1d1e1  br.s     loc_1D1FC
0x1d1e3  ldarg.1
0x1d1e4  ldarg.0
0x1d1e5  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d1ea  ldarg.0
0x1d1eb  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d1f0  ldarg.0
0x1d1f1  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d1f6  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::DrawMixedPath(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, unsigned int8[] pTypes, int32 nCount)
0x1d1fb  stloc.0
0x1d1fc  ldloc.0
0x1d1fd  ldc.i4.0
0x1d1fe  blt.s    loc_1D212
0x1d200  ldarg.1
0x1d201  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::EndPath()
0x1d206  stloc.0
0x1d207  ldloc.0
0x1d208  ldc.i4.0
0x1d209  blt.s    loc_1D212
0x1d20b  ldarg.1
0x1d20c  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::FillPath()
0x1d211  stloc.0
0x1d212  ldarg.1
0x1d213  ldarg.0
0x1d214  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d219  ldloca.s 5
0x1d21b  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::CleanupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype tagXFORM* oldTransform)
0x1d220  pop
0x1d221  ldloc.0
0x1d222  ret
```
