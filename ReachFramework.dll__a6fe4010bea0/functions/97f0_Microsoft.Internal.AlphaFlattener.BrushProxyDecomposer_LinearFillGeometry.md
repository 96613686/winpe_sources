# Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::LinearFillGeometry

- ea: `0x97f0`
- end: `0x9976`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::LinearFillGeometry`
- size: `390`
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
- `0x81d0`
- `0x8310`
- `0x8390`
- `0x97f0`
- `0x9b00`

## pseudocode

```c

```

## disassembly

```asm
0x97f0  ldc.i4.0
0x97f1  stloc.0
0x97f2  ldnull
0x97f3  stloc.1
0x97f4  ldc.r8   0.0
0x97fd  stloc.2
0x97fe  ldc.i4.1
0x97ff  stloc.3
0x9800  ldarg.1
0x9801  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x9806  isinst   [PresentationCore]System.Windows.Media.LinearGradientBrush
0x980b  stloc.1
0x980c  ldarg.1
0x980d  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::get_OpacityMask()
0x9812  stloc.s  4
0x9814  ldarg.1
0x9815  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x981a  stloc.s  5
0x981c  ldloc.1
0x981d  brfalse.s loc_9828
0x981f  ldarg.1
0x9820  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x9825  stloc.2
0x9826  br.s     loc_983F
0x9828  ldloc.s  4
0x982a  callvirt instance class [PresentationCore]System.Windows.Media.Brush Microsoft.Internal.AlphaFlattener.BrushProxy::get_Brush()
0x982f  isinst   [PresentationCore]System.Windows.Media.LinearGradientBrush
0x9834  stloc.1
0x9835  ldloc.s  4
0x9837  callvirt instance float64 Microsoft.Internal.AlphaFlattener.BrushProxy::get_Opacity()
0x983c  stloc.2
0x983d  ldc.i4.1
0x983e  stloc.0
0x983f  ldarg.1
0x9840  ldnull
0x9841  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_OpacityMask(class Microsoft.Internal.AlphaFlattener.BrushProxy value)
0x9846  ldloc.1
0x9847  ldarg.s  6
0x9849  ldloc.2
0x984a  newobj   instance void Microsoft.Internal.AlphaFlattener.LinearGradientFlattener::.ctor(class [PresentationCore]System.Windows.Media.LinearGradientBrush brush, class [PresentationCore]System.Windows.Media.Geometry geometry, float64 opacity)
0x984f  stloc.s  6
0x9851  ldloc.s  6
0x9853  callvirt instance int32 Microsoft.Internal.AlphaFlattener.LinearGradientFlattener::get_Steps()
0x9858  stloc.s  7
0x985a  ldarg.0
0x985b  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9860  brfalse.s loc_987C
0x9862  ldloc.s  7
0x9864  ldc.i4   0x1000
0x9869  ble.s    loc_9889
0x986b  ldarg.0
0x986c  ldc.r8   1.0
0x9875  stfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x987a  ldc.i4.1
0x987b  ret
0x987c  ldarg.0
0x987d  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x9882  ldarg.s  6
0x9884  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PushClip(class [PresentationCore]System.Windows.Media.Geometry)
0x9889  ldc.i4.0
0x988a  stloc.s  8
0x988c  br       loc_9948
0x9891  ldloc.s  6
0x9893  ldloc.s  8
0x9895  ldloca.s 9
0x9897  callvirt instance class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.AlphaFlattener.LinearGradientFlattener::GetSlice(int32 i, [out] valuetype [PresentationCore]System.Windows.Media.Color& color)
0x989c  stloc.s  0xA
0x989e  ldloc.0
0x989f  brfalse.s loc_98D0
0x98a1  ldarg.1
0x98a2  ldloc.s  5
0x98a4  ldloca.s 9
0x98a6  call     instance float32 [PresentationCore]System.Windows.Media.Color::get_ScA()
0x98ab  conv.r8
0x98ac  call     float64 Microsoft.Internal.AlphaFlattener.Utility::NormalizeOpacity(float64 value)
0x98b1  mul
0x98b2  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_Opacity(float64 value)
0x98b7  ldarg.3
0x98b8  brfalse.s loc_98C5
0x98ba  ldarg.1
0x98bb  ldarg.2
0x98bc  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x98c1  stloc.s  0xB
0x98c3  br.s     loc_990F
0x98c5  ldarg.2
0x98c6  ldarg.1
0x98c7  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x98cc  stloc.s  0xB
0x98ce  br.s     loc_990F
0x98d0  ldloc.s  4
0x98d2  brtrue.s loc_98E5
0x98d4  ldc.i4.0
0x98d5  ldloc.s  9
0x98d7  ldarg.2
0x98d8  ldarg.3
0x98d9  ldc.i4.0
0x98da  ceq
0x98dc  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x98e1  stloc.s  0xB
0x98e3  br.s     loc_990F
0x98e5  ldc.i4.0
0x98e6  ldloc.s  9
0x98e8  ldloc.s  4
0x98ea  ldc.i4.0
0x98eb  call     class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendColorWithBrush(bool opacityOnly, valuetype [PresentationCore]System.Windows.Media.Color colorA, class Microsoft.Internal.AlphaFlattener.BrushProxy brushB, bool reverse)
0x98f0  stloc.s  0xB
0x98f2  ldloc.s  0xB
0x98f4  brfalse.s loc_990F
0x98f6  ldarg.3
0x98f7  brfalse.s loc_9905
0x98f9  ldloc.s  0xB
0x98fb  ldarg.2
0x98fc  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x9901  stloc.s  0xB
0x9903  br.s     loc_990F
0x9905  ldarg.2
0x9906  ldloc.s  0xB
0x9908  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::BlendBrush(class Microsoft.Internal.AlphaFlattener.BrushProxy brushB)
0x990d  stloc.s  0xB
0x990f  ldloc.s  0xB
0x9911  brtrue.s loc_9917
0x9913  ldc.i4.0
0x9914  stloc.3
0x9915  br.s     loc_9926
0x9917  ldarg.0
0x9918  ldloc.s  0xB
0x991a  ldarg.s  4
0x991c  ldarg.s  5
0x991e  ldloc.s  0xA
0x9920  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy one, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry geometry)
0x9925  stloc.3
0x9926  ldloc.3
0x9927  brfalse.s loc_9951
0x9929  ldarg.0
0x992a  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x992f  brfalse.s loc_9942
0x9931  ldarg.0
0x9932  ldfld    float64 Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_cost
0x9937  ldc.r8   0.0
0x9940  bgt.s    loc_9951
0x9942  ldloc.s  8
0x9944  ldc.i4.1
0x9945  add
0x9946  stloc.s  8
0x9948  ldloc.s  8
0x994a  ldloc.s  7
0x994c  blt      loc_9891
0x9951  ldarg.1
0x9952  ldloc.s  4
0x9954  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_OpacityMask(class Microsoft.Internal.AlphaFlattener.BrushProxy value)
0x9959  ldarg.1
0x995a  ldloc.s  5
0x995c  callvirt instance void Microsoft.Internal.AlphaFlattener.BrushProxy::set_Opacity(float64 value)
0x9961  ldarg.0
0x9962  ldfld    bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_costing
0x9967  brtrue.s loc_9974
0x9969  ldarg.0
0x996a  ldfld    class [System.Printing]System.Printing.ILegacyDevice Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::_dc
0x996f  callvirt instance void [System.Printing]System.Printing.ILegacyDevice::PopClip()
0x9974  ldloc.3
0x9975  ret
```
