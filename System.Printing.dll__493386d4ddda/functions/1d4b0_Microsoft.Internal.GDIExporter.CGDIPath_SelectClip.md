# Microsoft.Internal.GDIExporter.CGDIPath::SelectClip

- ea: `0x1d4b0`
- end: `0x1d594`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::SelectClip`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1f490`

## callees

- `0x1c530`
- `0x1c5e0`
- `0x1c620`
- `0x1c650`
- `0x1c6d0`
- `0x1c760`
- `0x1c7d0`
- `0x1c7f0`
- `0x1c950`
- `0x1c980`
- `0x1d480`
- `0x1d4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1d4b0  ldarg.0
0x1d4b1  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1d4b6  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d4bb  ldc.i4.0
0x1d4bc  stloc.0
0x1d4bd  ldarg.0
0x1d4be  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d4c3  ldc.i4.0
0x1d4c4  ble      loc_1D592
0x1d4c9  ldarg.1
0x1d4ca  ldarg.0
0x1d4cb  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d4d0  ldloca.s 3
0x1d4d2  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) valuetype tagXFORM* oldTransform)
0x1d4d7  pop
0x1d4d8  ldarg.1
0x1d4d9  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::BeginPath()
0x1d4de  stloc.0
0x1d4df  ldloc.0
0x1d4e0  ldc.i4.0
0x1d4e1  blt      loc_1D583
0x1d4e6  ldarg.1
0x1d4e7  ldarg.0
0x1d4e8  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_PathFillMode
0x1d4ed  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetPolyFillMode(int32 polyfillmode)
0x1d4f2  pop
0x1d4f3  ldarg.0
0x1d4f4  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d4f9  stloc.2
0x1d4fa  ldloc.2
0x1d4fb  ldc.i4.1
0x1d4fc  and
0x1d4fd  brfalse.s loc_1D538
0x1d4ff  ldarg.0
0x1d500  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d505  stloc.1
0x1d506  ldloc.1
0x1d507  ldc.i4.1
0x1d508  bne.un.s loc_1D520
0x1d50a  ldarg.1
0x1d50b  ldarg.0
0x1d50c  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d511  ldc.i4.0
0x1d512  ldarg.0
0x1d513  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d518  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::Polygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offset, int32 nCount)
0x1d51d  stloc.0
0x1d51e  br.s     loc_1D56C
0x1d520  ldarg.1
0x1d521  ldarg.0
0x1d522  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d527  ldc.i4.0
0x1d528  ldarg.0
0x1d529  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d52e  ldc.i4.0
0x1d52f  ldloc.1
0x1d530  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::PolyPolygon(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 offsetP, unsigned int32[] pPolyCounts, int32 offsetC, int32 nCount)
0x1d535  stloc.0
0x1d536  br.s     loc_1D56C
0x1d538  ldloc.2
0x1d539  ldc.i4.s 0x10
0x1d53b  and
0x1d53c  brfalse.s loc_1D553
0x1d53e  ldarg.1
0x1d53f  ldarg.0
0x1d540  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d545  ldarg.0
0x1d546  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d54b  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::PolyBezier(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, int32 nCount)
0x1d550  stloc.0
0x1d551  br.s     loc_1D56C
0x1d553  ldarg.1
0x1d554  ldarg.0
0x1d555  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d55a  ldarg.0
0x1d55b  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d560  ldarg.0
0x1d561  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d566  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::DrawMixedPath(valuetype Microsoft.Internal.GDIExporter.PointI[] pPoints, unsigned int8[] pTypes, int32 nCount)
0x1d56b  stloc.0
0x1d56c  ldloc.0
0x1d56d  ldc.i4.0
0x1d56e  blt.s    loc_1D583
0x1d570  ldarg.1
0x1d571  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::EndPath()
0x1d576  stloc.0
0x1d577  ldloc.0
0x1d578  ldc.i4.0
0x1d579  blt.s    loc_1D583
0x1d57b  ldarg.1
0x1d57c  ldarg.2
0x1d57d  call     instance int32 Microsoft.Internal.GDIExporter.CGDIDevice::SelectClipPath(int32 iMode)
0x1d582  stloc.0
0x1d583  ldarg.1
0x1d584  ldarg.0
0x1d585  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d58a  ldloca.s 3
0x1d58c  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::CleanupForIncreasedResolution(int32 resolutionMultiplier, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype tagXFORM* oldTransform)
0x1d591  pop
0x1d592  ldloc.0
0x1d593  ret
```
