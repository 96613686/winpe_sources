# FigureList::AddFigureToList

- ea: `0x14d690`
- end: `0x14d96d`
- name: `FigureList::AddFigureToList`
- size: `733`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x71260`
- `0x89a60`
- `0x8a130`
- `0x8a170`
- `0x8a190`
- `0x8a1e0`
- `0x8a2e0`
- `0x8a590`
- `0x8bef0`
- `0x8d1e0`
- `0x8d8e0`
- `0x8dbe0`
- `0x8de30`
- `0x146e40`
- `0x14d680`
- `0x14d690`

## string_xrefs

- `0x14d723`: `PathGeometry_InternalReadBackError`
- `0x14d80a`: `PathGeometry_InternalReadBackError`
- `0x14d932`: `PathGeometry_InternalReadBackError`

## pseudocode

```c

```

## disassembly

```asm
0x14d690  ldarg.s  4
0x14d692  ldc.i4.1
0x14d693  blt.un   loc_14D96C
0x14d698  ldarg.s  6
0x14d69a  ldc.i4.1
0x14d69b  blt.un   loc_14D96C
0x14d6a0  newobj   instance void System.Windows.Media.PathFigure::.ctor()
0x14d6a5  stloc.3
0x14d6a6  ldloc.3
0x14d6a7  ldarg.1
0x14d6a8  callvirt instance void System.Windows.Media.PathFigure::set_IsFilled(bool value)
0x14d6ad  ldloc.3
0x14d6ae  ldarg.3
0x14d6af  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d6b4  conv.r8
0x14d6b5  ldarg.3
0x14d6b6  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d6bb  conv.r8
0x14d6bc  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d6c1  callvirt instance void System.Windows.Media.PathFigure::set_StartPoint(valuetype [WindowsBase]System.Windows.Point value)
0x14d6c6  ldc.i4.1
0x14d6c7  stloc.0
0x14d6c8  ldc.i4.0
0x14d6c9  stloc.1
0x14d6ca  ldc.i4.0
0x14d6cb  stloc.2
0x14d6cc  br       loc_14D946
0x14d6d1  ldarg.s  5
0x14d6d3  ldloc.2
0x14d6d4  add
0x14d6d5  ldind.u1
0x14d6d6  ldc.i4.3
0x14d6d7  and
0x14d6d8  conv.u1
0x14d6d9  stloc.s  0xD
0x14d6db  ldc.i4.1
0x14d6dc  stloc.1
0x14d6dd  br.s     loc_14D6E3
0x14d6df  ldloc.1
0x14d6e0  ldc.i4.1
0x14d6e1  add
0x14d6e2  stloc.1
0x14d6e3  ldloc.2
0x14d6e4  ldloc.1
0x14d6e5  add
0x14d6e6  conv.i8
0x14d6e7  ldarg.s  6
0x14d6e9  conv.u8
0x14d6ea  bge.s    loc_14D6FA
0x14d6ec  ldarg.s  5
0x14d6ee  ldloc.2
0x14d6ef  add
0x14d6f0  ldind.u1
0x14d6f1  ldarg.s  5
0x14d6f3  ldloc.2
0x14d6f4  ldloc.1
0x14d6f5  add
0x14d6f6  add
0x14d6f7  ldind.u1
0x14d6f8  beq.s    loc_14D6DF
0x14d6fa  ldarg.s  5
0x14d6fc  ldloc.2
0x14d6fd  add
0x14d6fe  ldind.u1
0x14d6ff  ldc.i4.4
0x14d700  and
0x14d701  ldc.i4.0
0x14d702  ceq
0x14d704  stloc.s  7
0x14d706  ldarg.s  5
0x14d708  ldloc.2
0x14d709  add
0x14d70a  ldind.u1
0x14d70b  ldc.i4.8
0x14d70c  and
0x14d70d  ldc.i4.0
0x14d70e  cgt.un
0x14d710  stloc.s  6
0x14d712  ldloc.s  0xD
0x14d714  ldc.i4.1
0x14d715  bne.un   loc_14D7F3
0x14d71a  ldloc.0
0x14d71b  ldloc.1
0x14d71c  add
0x14d71d  conv.i8
0x14d71e  ldarg.s  4
0x14d720  conv.u8
0x14d721  ble.s    loc_14D733
0x14d723  ldstr    aPathgeometryIn// "PathGeometry_InternalReadBackError"
0x14d728  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14d72d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x14d732  throw
0x14d733  ldloc.1
0x14d734  ldc.i4.1
0x14d735  ble      loc_14D7AF
0x14d73a  newobj   instance void System.Windows.Media.PointCollection::.ctor()
0x14d73f  stloc.s  0xA
0x14d741  ldc.i4.0
0x14d742  stloc.s  5
0x14d744  br.s     loc_14D780
0x14d746  ldloc.s  0xA
0x14d748  ldarg.3
0x14d749  ldloc.0
0x14d74a  ldloc.s  5
0x14d74c  add
0x14d74d  conv.i
0x14d74e  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d754  mul
0x14d755  add
0x14d756  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d75b  conv.r8
0x14d75c  ldarg.3
0x14d75d  ldloc.0
0x14d75e  ldloc.s  5
0x14d760  add
0x14d761  conv.i
0x14d762  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d768  mul
0x14d769  add
0x14d76a  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d76f  conv.r8
0x14d770  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d775  callvirt instance void System.Windows.Media.PointCollection::Add(valuetype [WindowsBase]System.Windows.Point value)
0x14d77a  ldloc.s  5
0x14d77c  ldc.i4.1
0x14d77d  add
0x14d77e  stloc.s  5
0x14d780  ldloc.s  5
0x14d782  ldloc.1
0x14d783  blt.s    loc_14D746
0x14d785  ldloc.s  0xA
0x14d787  callvirt instance void [WindowsBase]System.Windows.Freezable::Freeze()
0x14d78c  ldloc.s  0xA
0x14d78e  ldloc.s  7
0x14d790  ldloc.s  6
0x14d792  newobj   instance void System.Windows.Media.PolyLineSegment::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [WindowsBase]System.Windows.Point> points, bool isStroked, bool isSmoothJoin)
0x14d797  stloc.s  0xC
0x14d799  ldloc.s  0xC
0x14d79b  callvirt instance void [WindowsBase]System.Windows.Freezable::Freeze()
0x14d7a0  ldloc.3
0x14d7a1  callvirt instance class System.Windows.Media.PathSegmentCollection System.Windows.Media.PathFigure::get_Segments()
0x14d7a6  ldloc.s  0xC
0x14d7a8  callvirt instance void System.Windows.Media.PathSegmentCollection::Add(class System.Windows.Media.PathSegment value)
0x14d7ad  br.s     loc_14D7EA
0x14d7af  ldloc.3
0x14d7b0  callvirt instance class System.Windows.Media.PathSegmentCollection System.Windows.Media.PathFigure::get_Segments()
0x14d7b5  ldarg.3
0x14d7b6  ldloc.0
0x14d7b7  conv.i
0x14d7b8  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d7be  mul
0x14d7bf  add
0x14d7c0  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d7c5  conv.r8
0x14d7c6  ldarg.3
0x14d7c7  ldloc.0
0x14d7c8  conv.i
0x14d7c9  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d7cf  mul
0x14d7d0  add
0x14d7d1  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d7d6  conv.r8
0x14d7d7  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d7dc  ldloc.s  7
0x14d7de  ldloc.s  6
0x14d7e0  newobj   instance void System.Windows.Media.LineSegment::.ctor(valuetype [WindowsBase]System.Windows.Point point, bool isStroked, bool isSmoothJoin)
0x14d7e5  callvirt instance void System.Windows.Media.PathSegmentCollection::Add(class System.Windows.Media.PathSegment value)
0x14d7ea  ldloc.0
0x14d7eb  ldloc.1
0x14d7ec  add
0x14d7ed  stloc.0
0x14d7ee  br       loc_14D942
0x14d7f3  ldloc.s  0xD
0x14d7f5  ldc.i4.2
0x14d7f6  bne.un   loc_14D932
0x14d7fb  ldloc.1
0x14d7fc  ldc.i4.3
0x14d7fd  mul
0x14d7fe  stloc.s  9
0x14d800  ldloc.0
0x14d801  ldloc.s  9
0x14d803  add
0x14d804  conv.i8
0x14d805  ldarg.s  4
0x14d807  conv.u8
0x14d808  ble.s    loc_14D81A
0x14d80a  ldstr    aPathgeometryIn// "PathGeometry_InternalReadBackError"
0x14d80f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14d814  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x14d819  throw
0x14d81a  ldloc.1
0x14d81b  ldc.i4.1
0x14d81c  ble      loc_14D89A
0x14d821  newobj   instance void System.Windows.Media.PointCollection::.ctor()
0x14d826  stloc.s  8
0x14d828  ldc.i4.0
0x14d829  stloc.s  4
0x14d82b  br.s     loc_14D867
0x14d82d  ldloc.s  8
0x14d82f  ldarg.3
0x14d830  ldloc.0
0x14d831  ldloc.s  4
0x14d833  add
0x14d834  conv.i
0x14d835  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d83b  mul
0x14d83c  add
0x14d83d  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d842  conv.r8
0x14d843  ldarg.3
0x14d844  ldloc.0
0x14d845  ldloc.s  4
0x14d847  add
0x14d848  conv.i
0x14d849  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d84f  mul
0x14d850  add
0x14d851  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d856  conv.r8
0x14d857  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d85c  callvirt instance void System.Windows.Media.PointCollection::Add(valuetype [WindowsBase]System.Windows.Point value)
0x14d861  ldloc.s  4
0x14d863  ldc.i4.1
0x14d864  add
0x14d865  stloc.s  4
0x14d867  ldloc.s  4
0x14d869  ldloc.s  9
0x14d86b  blt.s    loc_14D82D
0x14d86d  ldloc.s  8
0x14d86f  callvirt instance void [WindowsBase]System.Windows.Freezable::Freeze()
0x14d874  ldloc.s  8
0x14d876  ldloc.s  7
0x14d878  ldloc.s  6
0x14d87a  newobj   instance void System.Windows.Media.PolyBezierSegment::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [WindowsBase]System.Windows.Point> points, bool isStroked, bool isSmoothJoin)
0x14d87f  stloc.s  0xB
0x14d881  ldloc.s  0xB
0x14d883  callvirt instance void [WindowsBase]System.Windows.Freezable::Freeze()
0x14d888  ldloc.3
0x14d889  callvirt instance class System.Windows.Media.PathSegmentCollection System.Windows.Media.PathFigure::get_Segments()
0x14d88e  ldloc.s  0xB
0x14d890  callvirt instance void System.Windows.Media.PathSegmentCollection::Add(class System.Windows.Media.PathSegment value)
0x14d895  br       loc_14D92B
0x14d89a  ldloc.3
0x14d89b  callvirt instance class System.Windows.Media.PathSegmentCollection System.Windows.Media.PathFigure::get_Segments()
0x14d8a0  ldarg.3
0x14d8a1  ldloc.0
0x14d8a2  conv.i
0x14d8a3  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d8a9  mul
0x14d8aa  add
0x14d8ab  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d8b0  conv.r8
0x14d8b1  ldarg.3
0x14d8b2  ldloc.0
0x14d8b3  conv.i
0x14d8b4  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d8ba  mul
0x14d8bb  add
0x14d8bc  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d8c1  conv.r8
0x14d8c2  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d8c7  ldarg.3
0x14d8c8  ldloc.0
0x14d8c9  ldc.i4.1
0x14d8ca  add
0x14d8cb  conv.i
0x14d8cc  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d8d2  mul
0x14d8d3  add
0x14d8d4  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d8d9  conv.r8
0x14d8da  ldarg.3
0x14d8db  ldloc.0
0x14d8dc  ldc.i4.1
0x14d8dd  add
0x14d8de  conv.i
0x14d8df  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d8e5  mul
0x14d8e6  add
0x14d8e7  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::Y
0x14d8ec  conv.r8
0x14d8ed  newobj   instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x14d8f2  ldarg.3
0x14d8f3  ldloc.0
0x14d8f4  ldc.i4.2
0x14d8f5  add
0x14d8f6  conv.i
0x14d8f7  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d8fd  mul
0x14d8fe  add
0x14d8ff  ldfld    float32 System.Windows.Media.Composition.MilPoint2F::X
0x14d904  conv.r8
0x14d905  ldarg.3
0x14d906  ldloc.0
0x14d907  ldc.i4.2
0x14d908  add
0x14d909  conv.i
0x14d90a  sizeof   System.Windows.Media.Composition.MilPoint2F
0x14d910  mul
0x14d911  add
  ... truncated ...
```
