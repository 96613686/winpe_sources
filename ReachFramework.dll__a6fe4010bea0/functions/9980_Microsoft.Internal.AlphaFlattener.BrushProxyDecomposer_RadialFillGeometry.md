# Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::RadialFillGeometry

- ea: `0x9980`
- end: `0x9afb`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::RadialFillGeometry`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x9b00`

## callees

- `0x40a0`
- `0x52e0`
- `0x76a0`
- `0x7830`
- `0x7840`
- `0x7850`
- `0x7860`
- `0x7870`
- `0x84e0`
- `0x87f0`
- `0x8900`
- `0x9980`
- `0x9b00`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldc.i4.0
0x9981  stloc.0
0x9982  ldnull
0x9983  stloc.1
0x9984  ldc.r8   0.0
0x998d  stloc.2
0x998e  ldarg.1
0x998f  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x9994  isinst   [PresentationCore]System.Windows.Media.RadialGradientBrush
0x9999  stloc.1
0x999a  ldarg.1
0x999b  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::get_OpacityMask()
0x99a0  stloc.3
0x99a1  ldarg.1
0x99a2  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x99a7  stloc.s  4
0x99a9  ldloc.1
0x99aa  brfalse.s loc_99B5
0x99ac  ldarg.1
0x99ad  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x99b2  stloc.2
0x99b3  br.s     loc_99CA
0x99b5  ldloc.3
0x99b6  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x99bb  isinst   [PresentationCore]System.Windows.Media.RadialGradientBrush
0x99c0  stloc.1
0x99c1  ldloc.3
0x99c2  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x99c7  stloc.2
0x99c8  ldc.i4.1
0x99c9  stloc.0
0x99ca  ldarg.1
0x99cb  ldnull
0x99cc  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_OpacityMask(class Microsoft.Internal.AlphaFlattener.BrushProxy value)
0x99d1  ldloc.1
0x99d2  ldarg.s  6
0x99d4  ldloc.2
0x99d5  newobj   instance void Microsoft.Internal.AlphaFlattener.RadialGradientFlattener::.ctor(class [PresentationCore]System.Windows.Media.RadialGradientBrush b, class [PresentationCore]System.Windows.Media.Geometry shape, float64 opacity)
0x99da  stloc.s  5
0x99dc  ldloc.s  5
0x99de  callvirt instance int32 Microsoft.Internal.AlphaFlattener.RadialGradientFlattener::get_Steps()
0x99e3  stloc.s  6
0x99e5  ldarg.0
0x99e6  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x99eb  brfalse.s loc_9A07
0x99ed  ldloc.s  6
0x99ef  ldc.i4   0x1000
0x99f4  ble.s    loc_9A14
0x99f6  ldarg.0
0x99f7  ldc.r8   1.0
0x9a00  stfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x9a05  ldc.i4.1
0x9a06  ret
0x9a07  ldarg.0
0x9a08  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9a0d  ldarg.s  6
0x9a0f  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PushClip(class [PresentationCore]System.Windows.Media.Geometry)
0x9a14  ldc.i4.1
0x9a15  stloc.s  7
0x9a17  ldloc.s  6
0x9a19  stloc.s  8
0x9a1b  br       loc_9ACE
0x9a20  ldloc.s  5
0x9a22  ldloc.s  8
0x9a24  ldloca.s 9
0x9a26  callvirt instance class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.AlphaFlattener.RadialGradientFlattener::GetSlice(int32 i, [out] valuetype [PresentationCore]System.Windows.Media.Color& color)
0x9a2b  stloc.s  0xA
0x9a2d  ldnull
0x9a2e  stloc.s  0xB
0x9a30  ldloc.0
0x9a31  brfalse.s loc_9A62
0x9a33  ldarg.1
0x9a34  ldloc.s  4
0x9a36  ldloca.s 9
0x9a38  call     instance float32 [PresentationCore]System.Windows.Media.Color::get_ScA()
0x9a3d  conv.r8
0x9a3e  call     float64 Microsoft.Internal.AlphaFlattener.Utility::NormalizeOpacity(float64 value)
0x9a43  mul
0x9a44  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_Opacity(float64 value)
0x9a49  ldarg.3
0x9a4a  brfalse.s loc_9A57
0x9a4c  ldarg.1
0x9a4d  ldarg.2
0x9a4e  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x9a53  stloc.s  0xB
0x9a55  br.s     loc_9A9B
0x9a57  ldarg.2
0x9a58  ldarg.1
0x9a59  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x9a5e  stloc.s  0xB
0x9a60  br.s     loc_9A9B
0x9a62  ldloc.3
0x9a63  brtrue.s loc_9A76
0x9a65  ldc.i4.0
0x9a66  ldloc.s  9
0x9a68  ldarg.2
0x9a69  ldarg.3
0x9a6a  ldc.i4.0
0x9a6b  ceq
0x9a6d  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x9a72  stloc.s  0xB
0x9a74  br.s     loc_9A9B
0x9a76  ldc.i4.0
0x9a77  ldloc.s  9
0x9a79  ldloc.3
0x9a7a  ldc.i4.0
0x9a7b  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x9a80  stloc.s  0xB
0x9a82  ldarg.3
0x9a83  brfalse.s loc_9A91
0x9a85  ldloc.s  0xB
0x9a87  ldarg.2
0x9a88  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x9a8d  stloc.s  0xB
0x9a8f  br.s     loc_9A9B
0x9a91  ldarg.2
0x9a92  ldloc.s  0xB
0x9a94  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x9a99  stloc.s  0xB
0x9a9b  ldarg.0
0x9a9c  ldloc.s  0xB
0x9a9e  ldarg.s  4
0x9aa0  ldarg.s  5
0x9aa2  ldloc.s  0xA
0x9aa4  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy one, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry geometry)
0x9aa9  stloc.s  7
0x9aab  ldloc.s  7
0x9aad  brfalse.s loc_9AD6
0x9aaf  ldarg.0
0x9ab0  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9ab5  brfalse.s loc_9AC8
0x9ab7  ldarg.0
0x9ab8  ldfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x9abd  ldc.r8   0.0
0x9ac6  bgt.s    loc_9AD6
0x9ac8  ldloc.s  8
0x9aca  ldc.i4.1
0x9acb  sub
0x9acc  stloc.s  8
0x9ace  ldloc.s  8
0x9ad0  ldc.i4.0
0x9ad1  bgt      loc_9A20
0x9ad6  ldarg.1
0x9ad7  ldloc.3
0x9ad8  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_OpacityMask(class Microsoft.Internal.AlphaFlattener.BrushProxy value)
0x9add  ldarg.1
0x9ade  ldloc.s  4
0x9ae0  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_Opacity(float64 value)
0x9ae5  ldarg.0
0x9ae6  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9aeb  brtrue.s loc_9AF8
0x9aed  ldarg.0
0x9aee  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9af3  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PopClip()
0x9af8  ldloc.s  7
0x9afa  ret
```
