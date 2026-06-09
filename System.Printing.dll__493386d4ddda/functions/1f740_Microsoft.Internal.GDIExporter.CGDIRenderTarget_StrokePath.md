# Microsoft.Internal.GDIExporter.CGDIRenderTarget::StrokePath

- ea: `0x1f740`
- end: `0x1f8c8`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::StrokePath`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1ee90`

## callees

- `0xf70`
- `0x1bf30`
- `0x1bf40`
- `0x1bf80`
- `0x1c010`
- `0x1c080`
- `0x1c0f0`
- `0x1cc10`
- `0x1d0a0`
- `0x1d230`
- `0x1d480`
- `0x1d490`
- `0x1f740`
- `0x1f8d0`
- `0x22230`
- `0x222b0`

## string_xrefs

- `0x1f76f`: `StrokePath skipping out of bounds geometry\n`
- `0x1f8a0`: `PathGeometry.GetWidenedPathGeometry failed.`

## pseudocode

```c

```

## disassembly

```asm
0x1f740  ldarg.2
0x1f741  ldnull
0x1f742  bne.un.s loc_1F747
0x1f744  ldc.i4.0
0x1f745  br.s     loc_1F748
0x1f747  ldc.i4.1
0x1f748  stloc.s  8
0x1f74a  ldloc.s  8
0x1f74c  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1f751  ldloca.s 9
0x1f753  initobj  [WindowsBase]System.Windows.Int32Rect
0x1f759  ldarg.1
0x1f75a  ldarg.2
0x1f75b  ldarg.0
0x1f75c  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f761  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f766  ldloca.s 9
0x1f768  call     instance bool Microsoft.Internal.GDIExporter.GeometryProxy::GetDrawBounds([hasfieldmarshal] class [PresentationCore]System.Windows.Media.Pen value, valuetype [WindowsBase]System.Windows.Media.Matrix pen, valuetype [WindowsBase]System.Windows.Int32Rect& transform)
0x1f76d  brtrue.s loc_1F77B
0x1f76f  ldstr    aStrokepathSkip// "StrokePath skipping out of bounds geome"...
0x1f774  call     void [System]System.Diagnostics.Debug::Write(string)
0x1f779  ldc.i4.0
0x1f77a  ret
0x1f77b  ldarg.2
0x1f77c  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_Thickness()
0x1f781  ldc.r8   0.0
0x1f78a  bne.un.s loc_1F78E
0x1f78c  ldc.i4.0
0x1f78d  ret
0x1f78e  ldarg.1
0x1f78f  ldarg.0
0x1f790  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f795  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f79a  ldarg.2
0x1f79b  call     class Microsoft.Internal.GDIExporter.CGDIPath Microsoft.Internal.GDIExporter.CGDIPath::CreateStrokePath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix matrix, class [PresentationCore]System.Windows.Media.Pen pen)
0x1f7a0  stloc.0
0x1f7a1  ldloc.0
0x1f7a2  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1f7a7  brfalse.s loc_1F7F0
0x1f7a9  ldarg.0
0x1f7aa  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f7af  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f7b4  call     bool Microsoft.Internal.GDIExporter.UniformScale([hasfieldmarshal] valuetype [WindowsBase]System.Windows.Media.Matrix value)
0x1f7b9  brfalse.s loc_1F7F0
0x1f7bb  ldarg.0
0x1f7bc  ldarg.2
0x1f7bd  ldarg.3
0x1f7be  ldarg.0
0x1f7bf  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f7c4  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f7c9  ldloc.0
0x1f7ca  ldarg.0
0x1f7cb  ldfld    unsigned int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_nDpiX
0x1f7d0  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::ConvertPen(class [PresentationCore]System.Windows.Media.Pen pen, class [PresentationCore]System.Windows.Media.Brush pStrokeBrush, valuetype [WindowsBase]System.Windows.Media.Matrix matrix, class Microsoft.Internal.GDIExporter.CGDIPath pPath, int32 dpi)
0x1f7d5  stloc.s  7
0x1f7d7  ldloc.s  7
0x1f7d9  brfalse.s loc_1F7F0
0x1f7db  ldloc.0
0x1f7dc  ldarg.0
0x1f7dd  ldloc.s  7
0x1f7df  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIPath::Draw(class Microsoft.Internal.GDIExporter.CGDIDevice dc, class Microsoft.Internal.GDIExporter.GdiSafeHandle pen)
0x1f7e4  stloc.1
0x1f7e5  ldloc.1
0x1f7e6  ldc.i4   0x80004001
0x1f7eb  bne.un   loc_1F8AA
0x1f7f0  ldarg.1
0x1f7f1  call     instance int32 Microsoft.Internal.GDIExporter.GeometryProxy::GetPointCount()
0x1f7f6  ldc.i4   0x400
0x1f7fb  ble.s    loc_1F81D
0x1f7fd  ldarg.1
0x1f7fe  ldarg.0
0x1f7ff  ldftn    instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::StrokePath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, class [PresentationCore]System.Windows.Media.Pen pPen, class [PresentationCore]System.Windows.Media.Brush pStrokeBrush)
0x1f805  newobj   instance void Microsoft.Internal.GDIExporter.RenderStrokePieceCallback::.ctor(object A_0, native int A_1)
0x1f80a  ldarg.2
0x1f80b  ldarg.3
0x1f80c  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.StrokeGeometrySplitter::RenderSubstrokes(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, class Microsoft.Internal.GDIExporter.RenderStrokePieceCallback callback, class [PresentationCore]System.Windows.Media.Pen callbackPen, class [PresentationCore]System.Windows.Media.Brush callbackBrush)
0x1f811  stloc.1
0x1f812  ldloc.1
0x1f813  ldc.i4   0x80004001
0x1f818  bne.un   loc_1F8AA
0x1f81d  ldarg.1
0x1f81e  call     instance class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::get_Geometry()
0x1f823  ldarg.2
0x1f824  call     instance class [PresentationCore]System.Windows.Media.PathGeometry [PresentationCore]System.Windows.Media.Geometry::GetWidenedPathGeometry(class [PresentationCore]System.Windows.Media.Pen)
0x1f829  stloc.3
0x1f82a  ldloc.3
0x1f82b  brtrue.s loc_1F835
0x1f82d  ldc.i4   0x80004005
0x1f832  stloc.1
0x1f833  br.s     loc_1F89F
0x1f835  ldloc.3
0x1f836  newobj   instance void Microsoft.Internal.GDIExporter.GeometryProxy::.ctor(class [PresentationCore]System.Windows.Media.Geometry geometry)
0x1f83b  stloc.2
0x1f83c  ldloc.0
0x1f83d  brfalse.s loc_1F851
0x1f83f  ldloc.0
0x1f840  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1f845  brfalse.s loc_1F851
0x1f847  ldloc.0
0x1f848  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::HasCurve()
0x1f84d  stloc.s  6
0x1f84f  br.s     loc_1F859
0x1f851  ldloc.2
0x1f852  call     instance bool Microsoft.Internal.GDIExporter.GeometryProxy::MayHaveCurves()
0x1f857  stloc.s  6
0x1f859  ldloc.s  6
0x1f85b  brfalse.s loc_1F894
0x1f85d  ldarg.2
0x1f85e  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_Thickness()
0x1f863  ldc.r8   0.800000011920929
0x1f86c  bge.un.s loc_1F894
0x1f86e  ldloc.3
0x1f86f  ldc.r8   0.25
0x1f878  ldc.i4.0
0x1f879  callvirt instance class [PresentationCore]System.Windows.Media.PathGeometry [PresentationCore]System.Windows.Media.Geometry::GetFlattenedPathGeometry(float64, valuetype [PresentationCore]System.Windows.Media.ToleranceType)
0x1f87e  stloc.s  5
0x1f880  ldloc.s  5
0x1f882  brtrue.s loc_1F88C
0x1f884  ldc.i4   0x80004005
0x1f889  stloc.1
0x1f88a  br.s     loc_1F8AA
0x1f88c  ldloc.2
0x1f88d  ldloc.s  5
0x1f88f  call     instance void Microsoft.Internal.GDIExporter.GeometryProxy::Attach(class [PresentationCore]System.Windows.Media.Geometry geometry)
0x1f894  ldarg.0
0x1f895  ldloc.2
0x1f896  ldarg.3
0x1f897  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillPath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, class [PresentationCore]System.Windows.Media.Brush pFillBrush)
0x1f89c  stloc.1
0x1f89d  br.s     loc_1F8AA
0x1f89f  ldc.i4.0
0x1f8a0  ldstr    aPathgeometryGe// "PathGeometry.GetWidenedPathGeometry fai"...
0x1f8a5  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f8aa  ldloc.0
0x1f8ab  brfalse.s loc_1F8C0
0x1f8ad  ldloc.0
0x1f8ae  isinst   [mscorlib]System.IDisposable
0x1f8b3  stloc.s  4
0x1f8b5  ldloc.s  4
0x1f8b7  brfalse.s loc_1F8C0
0x1f8b9  ldloc.s  4
0x1f8bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f8c0  ldarg.0
0x1f8c1  call     void [mscorlib]System.GC::KeepAlive(object)
0x1f8c6  ldloc.1
0x1f8c7  ret
```
