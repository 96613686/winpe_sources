# Microsoft.Internal.GDIExporter.CGDIPath::CreateFillPath

- ea: `0x1d090`
- end: `0x1d09a`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::CreateFillPath`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f490`
- `0x1f8d0`

## callees

- `0x1cfb0`

## pseudocode

```c

```

## disassembly

```asm
0x1d090  ldarg.0
0x1d091  ldarg.1
0x1d092  ldc.i4.1
0x1d093  ldnull
0x1d094  newobj   instance void Microsoft.Internal.GDIExporter.CGDIPath::.ctor(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix matrix, [hasfieldmarshal] bool ForFill, class [PresentationCore]System.Windows.Media.Pen pen)
0x1d099  ret
```
