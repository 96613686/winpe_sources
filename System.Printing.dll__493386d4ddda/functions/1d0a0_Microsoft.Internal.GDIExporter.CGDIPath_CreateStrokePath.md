# Microsoft.Internal.GDIExporter.CGDIPath::CreateStrokePath

- ea: `0x1d0a0`
- end: `0x1d0aa`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::CreateStrokePath`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f740`

## callees

- `0x1cfb0`

## pseudocode

```c

```

## disassembly

```asm
0x1d0a0  ldarg.0
0x1d0a1  ldarg.1
0x1d0a2  ldc.i4.0
0x1d0a3  ldarg.2
0x1d0a4  newobj   instance void Microsoft.Internal.GDIExporter.CGDIPath::.ctor(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix matrix, [hasfieldmarshal] bool ForFill, class [PresentationCore]System.Windows.Media.Pen pen)
0x1d0a9  ret
```
