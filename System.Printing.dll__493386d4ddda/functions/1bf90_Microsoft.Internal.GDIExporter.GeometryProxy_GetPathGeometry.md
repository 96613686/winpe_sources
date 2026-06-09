# Microsoft.Internal.GDIExporter.GeometryProxy::GetPathGeometry

- ea: `0x1bf90`
- end: `0x1bfa2`
- name: `Microsoft.Internal.GDIExporter.GeometryProxy::GetPathGeometry`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1c080`

## callees

- `0x1c190`

## pseudocode

```c

```

## disassembly

```asm
0x1bf90  ldarg.0
0x1bf91  call     instance void Microsoft.Internal.GDIExporter.GeometryProxy::ConvertToPathGeometry()
0x1bf96  ldarg.0
0x1bf97  ldfld    class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::_geometry
0x1bf9c  castclass [PresentationCore]System.Windows.Media.PathGeometry
0x1bfa1  ret
```
