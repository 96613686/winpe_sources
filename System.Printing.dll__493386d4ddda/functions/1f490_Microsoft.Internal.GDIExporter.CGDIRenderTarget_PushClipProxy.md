# Microsoft.Internal.GDIExporter.CGDIRenderTarget::PushClipProxy

- ea: `0x1f490`
- end: `0x1f737`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::PushClipProxy`
- size: `679`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1ee30`
- `0x1fd10`
- `0x20d40`

## callees

- `0x2a0`
- `0x1bb40`
- `0x1bf80`
- `0x1bfe0`
- `0x1c160`
- `0x1cf70`
- `0x1d090`
- `0x1d480`
- `0x1d4b0`
- `0x1f490`

## string_xrefs

- `0x1f6b8`: `Invalid CGDIPath`

## pseudocode

```c

```

## disassembly

```asm
0x1f490  ldarg.0
0x1f491  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1f496  brfalse  loc_1F736
0x1f49b  ldarg.0
0x1f49c  ldfld    bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_startPage
0x1f4a1  ldstr    aStartpageHasNo// "StartPage has not been called yet (Push"...
0x1f4a6  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f4ab  ldarg.0
0x1f4ac  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_DeviceTransform
0x1f4b1  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetX()
0x1f4b6  conv.i4
0x1f4b7  neg
0x1f4b8  stloc.2
0x1f4b9  ldarg.0
0x1f4ba  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_DeviceTransform
0x1f4bf  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetY()
0x1f4c4  conv.i4
0x1f4c5  neg
0x1f4c6  stloc.1
0x1f4c7  ldarg.0
0x1f4c8  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f4cd  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f4d2  call     bool Microsoft.Internal.GDIExporter.IsTranslateOrScale([hasfieldmarshal] valuetype [WindowsBase]System.Windows.Media.Matrix value)
0x1f4d7  brfalse  loc_1F62A
0x1f4dc  ldloca.s 0xF
0x1f4de  initobj  [WindowsBase]System.Windows.Point
0x1f4e4  ldloca.s 0xE
0x1f4e6  initobj  [WindowsBase]System.Windows.Point
0x1f4ec  ldloc.2
0x1f4ed  conv.r8
0x1f4ee  ldarg.0
0x1f4ef  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f4f4  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetX()
0x1f4f9  sub
0x1f4fa  stloc.s  0xC
0x1f4fc  ldloca.s 0xF
0x1f4fe  ldloc.s  0xC
0x1f500  ldarg.0
0x1f501  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f506  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M11()
0x1f50b  div
0x1f50c  call     instance void [WindowsBase]System.Windows.Point::set_X(float64)
0x1f511  ldloc.1
0x1f512  conv.r8
0x1f513  ldarg.0
0x1f514  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f519  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetY()
0x1f51e  sub
0x1f51f  stloc.s  0xB
0x1f521  ldloca.s 0xF
0x1f523  ldloc.s  0xB
0x1f525  ldarg.0
0x1f526  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f52b  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M22()
0x1f530  div
0x1f531  call     instance void [WindowsBase]System.Windows.Point::set_Y(float64)
0x1f536  ldarg.0
0x1f537  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nWidth
0x1f53c  ldloc.2
0x1f53d  add
0x1f53e  conv.r8
0x1f53f  stloc.s  0xA
0x1f541  ldloc.s  0xA
0x1f543  ldarg.0
0x1f544  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f549  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetX()
0x1f54e  sub
0x1f54f  stloc.s  9
0x1f551  ldloca.s 0xE
0x1f553  ldloc.s  9
0x1f555  ldarg.0
0x1f556  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f55b  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M11()
0x1f560  div
0x1f561  call     instance void [WindowsBase]System.Windows.Point::set_X(float64)
0x1f566  ldarg.0
0x1f567  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nHeight
0x1f56c  ldloc.1
0x1f56d  add
0x1f56e  conv.r8
0x1f56f  stloc.s  8
0x1f571  ldloc.s  8
0x1f573  ldarg.0
0x1f574  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f579  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_OffsetY()
0x1f57e  sub
0x1f57f  stloc.s  7
0x1f581  ldloca.s 0xE
0x1f583  ldloc.s  7
0x1f585  ldarg.0
0x1f586  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f58b  call     instance float64 [WindowsBase]System.Windows.Media.Matrix::get_M22()
0x1f590  div
0x1f591  call     instance void [WindowsBase]System.Windows.Point::set_Y(float64)
0x1f596  ldarg.1
0x1f597  ldnull
0x1f598  call     instance valuetype [WindowsBase]System.Windows.Rect Microsoft.Internal.GDIExporter.GeometryProxy::GetBounds(class [PresentationCore]System.Windows.Media.Pen pen)
0x1f59d  stloc.s  0xD
0x1f59f  ldloca.s 0xD
0x1f5a1  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x1f5a6  ldloca.s 0xF
0x1f5a8  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x1f5ad  bgt.un.s loc_1F5EA
0x1f5af  ldloca.s 0xD
0x1f5b1  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x1f5b6  ldloca.s 0xF
0x1f5b8  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x1f5bd  bgt.un.s loc_1F5EA
0x1f5bf  ldloca.s 0xD
0x1f5c1  call     instance float64 [WindowsBase]System.Windows.Rect::get_Right()
0x1f5c6  ldloca.s 0xE
0x1f5c8  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x1f5cd  blt.un.s loc_1F5EA
0x1f5cf  ldloca.s 0xD
0x1f5d1  call     instance float64 [WindowsBase]System.Windows.Rect::get_Bottom()
0x1f5d6  ldloca.s 0xE
0x1f5d8  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x1f5dd  blt.un.s loc_1F5EA
0x1f5df  ldarg.1
0x1f5e0  call     instance bool Microsoft.Internal.GDIExporter.GeometryProxy::IsRectangle()
0x1f5e5  brtrue   loc_1F71F
0x1f5ea  ldloca.s 0xD
0x1f5ec  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x1f5f1  ldloca.s 0xF
0x1f5f3  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x1f5f8  ble.un.s loc_1F62A
0x1f5fa  ldloca.s 0xD
0x1f5fc  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x1f601  ldloca.s 0xF
0x1f603  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x1f608  ble.un.s loc_1F62A
0x1f60a  ldloca.s 0xD
0x1f60c  call     instance float64 [WindowsBase]System.Windows.Rect::get_Right()
0x1f611  ldloca.s 0xE
0x1f613  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x1f618  bge.un.s loc_1F62A
0x1f61a  ldloca.s 0xD
0x1f61c  call     instance float64 [WindowsBase]System.Windows.Rect::get_Bottom()
0x1f621  ldloca.s 0xE
0x1f623  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x1f628  blt.s    loc_1F6A0
0x1f62a  ldloca.s 6
0x1f62c  ldloc.2
0x1f62d  conv.r8
0x1f62e  ldloc.1
0x1f62f  conv.r8
0x1f630  ldarg.0
0x1f631  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nWidth
0x1f636  conv.r8
0x1f637  ldarg.0
0x1f638  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nHeight
0x1f63d  conv.r8
0x1f63e  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0x1f643  ldloca.s 6
0x1f645  ldc.r8   -0.1
0x1f64e  ldc.r8   -0.1
0x1f657  call     instance void [WindowsBase]System.Windows.Rect::Inflate(float64, float64)
0x1f65c  ldloc.s  6
0x1f65e  newobj   instance void [PresentationCore]System.Windows.Media.RectangleGeometry::.ctor(valuetype [WindowsBase]System.Windows.Rect)
0x1f663  stloc.3
0x1f664  ldarg.0
0x1f665  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f66a  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f66f  stloc.s  5
0x1f671  ldloca.s 5
0x1f673  call     instance bool [WindowsBase]System.Windows.Media.Matrix::get_HasInverse()
0x1f678  brfalse.s loc_1F6A0
0x1f67a  ldloca.s 5
0x1f67c  call     instance void [WindowsBase]System.Windows.Media.Matrix::Invert()
0x1f681  ldloc.3
0x1f682  ldloc.s  5
0x1f684  newobj   instance void [PresentationCore]System.Windows.Media.MatrixTransform::.ctor(valuetype [WindowsBase]System.Windows.Media.Matrix)
0x1f689  call     instance void [PresentationCore]System.Windows.Media.Geometry::set_Transform(class [PresentationCore]System.Windows.Media.Transform)
0x1f68e  ldarg.1
0x1f68f  call     instance class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::get_Geometry()
0x1f694  ldloc.3
0x1f695  call     instance valuetype [PresentationCore]System.Windows.Media.IntersectionDetail [PresentationCore]System.Windows.Media.Geometry::FillContainsWithDetail(class [PresentationCore]System.Windows.Media.Geometry)
0x1f69a  ldc.i4.3
0x1f69b  beq      loc_1F71F
0x1f6a0  ldarg.1
0x1f6a1  ldarg.0
0x1f6a2  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f6a7  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f6ac  call     class Microsoft.Internal.GDIExporter.CGDIPath Microsoft.Internal.GDIExporter.CGDIPath::CreateFillPath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix matrix)
0x1f6b1  stloc.0
0x1f6b2  ldloc.0
0x1f6b3  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1f6b8  ldstr    aInvalidCgdipat// "Invalid CGDIPath"
0x1f6bd  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f6c2  ldarg.0
0x1f6c3  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_clipLevel
0x1f6c8  brtrue.s loc_1F6D5
0x1f6ca  ldloc.0
0x1f6cb  ldarg.0
0x1f6cc  ldc.i4.5
0x1f6cd  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIPath::SelectClip(class Microsoft.Internal.GDIExporter.CGDIDevice dc, int32 mode)
0x1f6d2  pop
0x1f6d3  br.s     loc_1F6FE
0x1f6d5  ldarg.0
0x1f6d6  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1f6db  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::SaveDC(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc)
0x1f6e0  ldc.i4.0
0x1f6e1  bne.un.s loc_1F6E6
0x1f6e3  ldc.i4.0
0x1f6e4  br.s     loc_1F6E7
0x1f6e6  ldc.i4.1
0x1f6e7  stloc.s  4
0x1f6e9  ldloc.s  4
0x1f6eb  ldstr    aSavedcFailed// "SaveDC failed"
0x1f6f0  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f6f5  ldloc.0
0x1f6f6  ldarg.0
0x1f6f7  ldc.i4.1
0x1f6f8  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIPath::SelectClip(class Microsoft.Internal.GDIExporter.CGDIDevice dc, int32 mode)
0x1f6fd  pop
0x1f6fe  ldarg.0
0x1f6ff  dup
0x1f700  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_clipLevel
0x1f705  ldc.i4.1
0x1f706  add
0x1f707  stfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_clipLevel
0x1f70c  ldarg.0
0x1f70d  ldfld    class [mscorlib]System.Collections.Stack Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_state
0x1f712  ldc.i4.1
0x1f713  box      [mscorlib]System.Int32
0x1f718  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x1f71d  br.s     loc_1F730
0x1f71f  ldarg.0
0x1f720  ldfld    class [mscorlib]System.Collections.Stack Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_state
0x1f725  ldc.i4.2
0x1f726  box      [mscorlib]System.Int32
0x1f72b  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x1f730  ldarg.0
0x1f731  call     void [mscorlib]System.GC::KeepAlive(object)
0x1f736  ret
```
