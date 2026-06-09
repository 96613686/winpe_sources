# Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillPath

- ea: `0x1f8d0`
- end: `0x1f96e`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillPath`
- size: `158`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1ee90`
- `0x1ef70`
- `0x1f150`
- `0x1f740`
- `0x20d40`

## callees

- `0x1c010`
- `0x1c490`
- `0x1ce40`
- `0x1d090`
- `0x1d0b0`
- `0x1d480`
- `0x1f8d0`
- `0x1fd10`
- `0x20d40`

## string_xrefs

- `0x1f91d`: `Invalid CGDIPath`
- `0x1f8ee`: `FillPath skipping out of bounds geometry\n`

## pseudocode

```c

```

## disassembly

```asm
0x1f8d0  ldloca.s 4
0x1f8d2  initobj  [WindowsBase]System.Windows.Int32Rect
0x1f8d8  ldarg.1
0x1f8d9  ldnull
0x1f8da  ldarg.0
0x1f8db  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f8e0  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f8e5  ldloca.s 4
0x1f8e7  call     instance bool Microsoft.Internal.GDIExporter.GeometryProxy::GetDrawBounds([hasfieldmarshal] class [PresentationCore]System.Windows.Media.Pen value, valuetype [WindowsBase]System.Windows.Media.Matrix pen, valuetype [WindowsBase]System.Windows.Int32Rect& transform)
0x1f8ec  brtrue.s loc_1F8FA
0x1f8ee  ldstr    aFillpathSkippi// "FillPath skipping out of bounds geometr"...
0x1f8f3  call     void [System]System.Diagnostics.Debug::Write(string)
0x1f8f8  ldc.i4.0
0x1f8f9  ret
0x1f8fa  ldarg.0
0x1f8fb  ldarg.2
0x1f8fc  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::ConvertBrush(class [PresentationCore]System.Windows.Media.Brush brush)
0x1f901  stloc.3
0x1f902  ldloc.3
0x1f903  brfalse.s loc_1F942
0x1f905  ldarg.1
0x1f906  ldarg.0
0x1f907  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x1f90c  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1f911  call     class Microsoft.Internal.GDIExporter.CGDIPath Microsoft.Internal.GDIExporter.CGDIPath::CreateFillPath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix matrix)
0x1f916  stloc.1
0x1f917  ldloc.1
0x1f918  call     instance bool Microsoft.Internal.GDIExporter.CGDIPath::IsValid()
0x1f91d  ldstr    aInvalidCgdipat// "Invalid CGDIPath"
0x1f922  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f927  ldloc.1
0x1f928  ldarg.0
0x1f929  ldloc.3
0x1f92a  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIPath::Fill(class Microsoft.Internal.GDIExporter.CGDIDevice dc, class Microsoft.Internal.GDIExporter.GdiSafeHandle brush)
0x1f92f  stloc.0
0x1f930  ldloc.1
0x1f931  isinst   [mscorlib]System.IDisposable
0x1f936  stloc.2
0x1f937  ldloc.2
0x1f938  brfalse.s loc_1F959
0x1f93a  ldloc.2
0x1f93b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f940  br.s     loc_1F959
0x1f942  ldarg.0
0x1f943  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIDevice::GetCaps()
0x1f948  ldc.i4   0x1000
0x1f94d  and
0x1f94e  brfalse.s loc_1F961
0x1f950  ldarg.0
0x1f951  ldarg.1
0x1f952  ldarg.2
0x1f953  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillLinearGradient(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, class [PresentationCore]System.Windows.Media.Brush brush)
0x1f958  stloc.0
0x1f959  ldloc.0
0x1f95a  ldc.i4   0x80004001
0x1f95f  bne.un.s loc_1F96C
0x1f961  ldarg.0
0x1f962  ldarg.1
0x1f963  ldloca.s 4
0x1f965  ldarg.2
0x1f966  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::RasterizeShape(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Int32Rect& pBounds, class [PresentationCore]System.Windows.Media.Brush pFillBrush)
0x1f96b  stloc.0
0x1f96c  ldloc.0
0x1f96d  ret
```
