# Microsoft.Internal.GDIExporter.GeometryProxy::DoesGetDataHavePathGeometryConversion

- ea: `0x1c1c0`
- end: `0x1c1f9`
- name: `Microsoft.Internal.GDIExporter.GeometryProxy::DoesGetDataHavePathGeometryConversion`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1bfb0`
- `0x1c080`

## callees

- `0x1c1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c1c0  ldarg.0
0x1c1c1  ldfld    class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::_geometry
0x1c1c6  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c1cb  stloc.1
0x1c1cc  ldloc.1
0x1c1cd  ldtoken  [PresentationCore]System.Windows.Media.CombinedGeometry
0x1c1d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c1d7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c1dc  brtrue.s loc_1C1F4
0x1c1de  ldloc.1
0x1c1df  ldtoken  [PresentationCore]System.Windows.Media.GeometryGroup
0x1c1e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c1e9  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c1ee  brtrue.s loc_1C1F4
0x1c1f0  ldc.i4.0
0x1c1f1  stloc.0
0x1c1f2  br.s     loc_1C1F6
0x1c1f4  ldc.i4.1
0x1c1f5  stloc.0
0x1c1f6  ldloc.0
0x1c1f7  conv.u1
0x1c1f8  ret
```
