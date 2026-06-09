# System.Windows.Media.PathFigure::GetFlattenedPathFigure

- ea: `0x8a350`
- end: `0x8a3a1`
- name: `System.Windows.Media.PathFigure::GetFlattenedPathFigure`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x8a3b0`

## callees

- `0x84c50`
- `0x8a2e0`
- `0x8a350`
- `0x8a590`
- `0x8a730`
- `0x8a7b0`
- `0x8b120`
- `0x8b2c0`
- `0x146e40`

## string_xrefs

- `0x8a391`: `PathGeometry_InternalReadBackError`

## pseudocode

```c

```

## disassembly

```asm
0x8a350  newobj   instance void System.Windows.Media.PathGeometry::.ctor()
0x8a355  stloc.2
0x8a356  ldloc.2
0x8a357  callvirt instance class System.Windows.Media.PathFigureCollection System.Windows.Media.PathGeometry::get_Figures()
0x8a35c  ldarg.0
0x8a35d  callvirt instance void System.Windows.Media.PathFigureCollection::Add(class System.Windows.Media.PathFigure value)
0x8a362  ldloc.2
0x8a363  ldarg.1
0x8a364  ldarg.2
0x8a365  callvirt instance class System.Windows.Media.PathGeometry System.Windows.Media.Geometry::GetFlattenedPathGeometry(float64 tolerance, valuetype System.Windows.Media.ToleranceType type)
0x8a36a  stloc.1
0x8a36b  ldloc.1
0x8a36c  callvirt instance class System.Windows.Media.PathFigureCollection System.Windows.Media.PathGeometry::get_Figures()
0x8a371  callvirt instance int32 System.Windows.Media.PathFigureCollection::get_Count()
0x8a376  stloc.0
0x8a377  ldloc.0
0x8a378  brtrue.s loc_8A380
0x8a37a  newobj   instance void System.Windows.Media.PathFigure::.ctor()
0x8a37f  ret
0x8a380  ldloc.0
0x8a381  ldc.i4.1
0x8a382  bne.un.s loc_8A391
0x8a384  ldloc.1
0x8a385  callvirt instance class System.Windows.Media.PathFigureCollection System.Windows.Media.PathGeometry::get_Figures()
0x8a38a  ldc.i4.0
0x8a38b  callvirt instance class System.Windows.Media.PathFigure System.Windows.Media.PathFigureCollection::get_Item(int32 index)
0x8a390  ret
0x8a391  ldstr    aPathgeometryIn// "PathGeometry_InternalReadBackError"
0x8a396  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x8a39b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8a3a0  throw
```
