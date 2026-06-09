# Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry

- ea: `0x9b00`
- end: `0x9c0b`
- name: `Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::FillGeometry`
- size: `267`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x97f0`
- `0x9980`
- `0x9c10`
- `0x9e10`

## callees

- `0x7860`
- `0x78a0`
- `0x78d0`
- `0x9480`
- `0x97f0`
- `0x9980`
- `0x9b00`

## pseudocode

```c

```

## disassembly

```asm
0x9b00  ldnull
0x9b01  stloc.0
0x9b02  ldarg.1
0x9b03  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9b08  brtrue.s loc_9B3A
0x9b0a  ldarg.3
0x9b0b  ldarg.2
0x9b0c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x9b11  blt.s    loc_9B26
0x9b13  ldarg.0
0x9b14  ldarg.1
0x9b15  ldnull
0x9b16  ldarg.s  4
0x9b18  ldnull
0x9b19  call     valuetype [WindowsBase]System.Windows.Media.Matrix [WindowsBase]System.Windows.Media.Matrix::get_Identity()
0x9b1e  ldc.i4.0
0x9b1f  callvirt instance void Microsoft.Internal.AlphaFlattener.IProxyDrawingContext::DrawGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy brush, class Microsoft.Internal.AlphaFlattener.PenProxy pen, class [PresentationCore]System.Windows.Media.Geometry geometry, class [PresentationCore]System.Windows.Media.Geometry clip, valuetype [WindowsBase]System.Windows.Media.Matrix brushTrans, valuetype Microsoft.Internal.AlphaFlattener.ProxyDrawingFlags flags)
0x9b24  ldc.i4.1
0x9b25  ret
0x9b26  ldarg.2
0x9b27  ldarg.3
0x9b28  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9b2d  isinst   Microsoft.Internal.AlphaFlattener.BrushProxy
0x9b32  stloc.0
0x9b33  ldarg.3
0x9b34  ldc.i4.1
0x9b35  add
0x9b36  starg.s  3
0x9b38  br.s     loc_9B5F
0x9b3a  ldarg.1
0x9b3b  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9b40  ldc.i4.1
0x9b41  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9b46  isinst   Microsoft.Internal.AlphaFlattener.BrushProxy
0x9b4b  stloc.0
0x9b4c  ldarg.1
0x9b4d  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushList()
0x9b52  ldc.i4.0
0x9b53  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x9b58  isinst   Microsoft.Internal.AlphaFlattener.BrushProxy
0x9b5d  starg.s  1
0x9b5f  ldarg.1
0x9b60  callvirt instance valuetype BrushTypes Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushType()
0x9b65  stloc.1
0x9b66  ldloc.0
0x9b67  callvirt instance valuetype BrushTypes Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushType()
0x9b6c  stloc.2
0x9b6d  ldc.i4.1
0x9b6e  stloc.3
0x9b6f  ldc.i4.0
0x9b70  stloc.s  4
0x9b72  br       loc_9C01
0x9b77  ldloc.1
0x9b78  ldloc.2
0x9b79  blt.s    loc_9B80
0x9b7b  ldloc.s  4
0x9b7d  ldc.i4.1
0x9b7e  bne.un.s loc_9B96
0x9b80  ldarg.1
0x9b81  stloc.s  5
0x9b83  ldloc.0
0x9b84  starg.s  1
0x9b86  ldloc.s  5
0x9b88  stloc.0
0x9b89  ldloc.1
0x9b8a  stloc.s  6
0x9b8c  ldloc.2
0x9b8d  stloc.1
0x9b8e  ldloc.s  6
0x9b90  stloc.2
0x9b91  ldloc.3
0x9b92  ldc.i4.0
0x9b93  ceq
0x9b95  stloc.3
0x9b96  ldloc.1
0x9b97  ldc.i4.s 0x20
0x9b99  and
0x9b9a  brfalse.s loc_9BAA
0x9b9c  ldarg.0
0x9b9d  ldarg.1
0x9b9e  ldloc.0
0x9b9f  ldloc.3
0x9ba0  ldarg.2
0x9ba1  ldarg.3
0x9ba2  ldarg.s  4
0x9ba4  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::RadialFillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy radial, class Microsoft.Internal.AlphaFlattener.BrushProxy other, bool pre, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9ba9  ret
0x9baa  ldloc.1
0x9bab  ldc.i4.s 0x10
0x9bad  and
0x9bae  brfalse.s loc_9BBE
0x9bb0  ldarg.0
0x9bb1  ldarg.1
0x9bb2  ldloc.0
0x9bb3  ldloc.3
0x9bb4  ldarg.2
0x9bb5  ldarg.3
0x9bb6  ldarg.s  4
0x9bb8  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::LinearFillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy linear, class Microsoft.Internal.AlphaFlattener.BrushProxy other, bool pre, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9bbd  ret
0x9bbe  ldloc.1
0x9bbf  ldc.i4.s 0x40
0x9bc1  and
0x9bc2  brfalse.s loc_9BFB
0x9bc4  ldarg.1
0x9bc5  callvirt instance class Microsoft.Internal.AlphaFlattener.BrushProxy Microsoft.Internal.AlphaFlattener.BrushProxy::get_OpacityMask()
0x9bca  callvirt instance valuetype BrushTypes Microsoft.Internal.AlphaFlattener.BrushProxy::get_BrushType()
0x9bcf  stloc.s  7
0x9bd1  ldloc.s  7
0x9bd3  ldc.i4.s 0x20
0x9bd5  and
0x9bd6  brfalse.s loc_9BE6
0x9bd8  ldarg.0
0x9bd9  ldarg.1
0x9bda  ldloc.0
0x9bdb  ldloc.3
0x9bdc  ldarg.2
0x9bdd  ldarg.3
0x9bde  ldarg.s  4
0x9be0  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::RadialFillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy radial, class Microsoft.Internal.AlphaFlattener.BrushProxy other, bool pre, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9be5  ret
0x9be6  ldloc.s  7
0x9be8  ldc.i4.s 0x10
0x9bea  and
0x9beb  brfalse.s loc_9BFB
0x9bed  ldarg.0
0x9bee  ldarg.1
0x9bef  ldloc.0
0x9bf0  ldloc.3
0x9bf1  ldarg.2
0x9bf2  ldarg.3
0x9bf3  ldarg.s  4
0x9bf5  call     instance bool Microsoft.Internal.AlphaFlattener.BrushProxyDecomposer::LinearFillGeometry(class Microsoft.Internal.AlphaFlattener.BrushProxy linear, class Microsoft.Internal.AlphaFlattener.BrushProxy other, bool pre, class [mscorlib]System.Collections.ArrayList brushes, int32 from, class [PresentationCore]System.Windows.Media.Geometry shape)
0x9bfa  ret
0x9bfb  ldloc.s  4
0x9bfd  ldc.i4.1
0x9bfe  add
0x9bff  stloc.s  4
0x9c01  ldloc.s  4
0x9c03  ldc.i4.2
0x9c04  blt      loc_9B77
0x9c09  ldc.i4.0
0x9c0a  ret
```
