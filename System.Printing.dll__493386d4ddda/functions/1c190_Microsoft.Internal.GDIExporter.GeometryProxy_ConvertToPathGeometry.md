# Microsoft.Internal.GDIExporter.GeometryProxy::ConvertToPathGeometry

- ea: `0x1c190`
- end: `0x1c1be`
- name: `Microsoft.Internal.GDIExporter.GeometryProxy::ConvertToPathGeometry`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1bf90`
- `0x1bfb0`

## callees

- `0x1c190`

## pseudocode

```c

```

## disassembly

```asm
0x1c190  ldarg.0
0x1c191  ldfld    class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::_geometry
0x1c196  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c19b  ldtoken  [PresentationCore]System.Windows.Media.PathGeometry
0x1c1a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c1a5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c1aa  brfalse.s loc_1C1BD
0x1c1ac  ldarg.0
0x1c1ad  dup
0x1c1ae  ldfld    class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::_geometry
0x1c1b3  call     class [PresentationCore]System.Windows.Media.PathGeometry [PresentationCore]System.Windows.Media.PathGeometry::CreateFromGeometry(class [PresentationCore]System.Windows.Media.Geometry)
0x1c1b8  stfld    class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::_geometry
0x1c1bd  ret
```
