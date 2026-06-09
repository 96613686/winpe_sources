# System.Windows.Ink.StrokeCollection::Replace_0

- ea: `0x6fcf0`
- end: `0x6fe0e`
- name: `System.Windows.Ink.StrokeCollection::Replace_0`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x6fcc0`

## callees

- `0x6fb90`
- `0x6fcf0`
- `0x70170`
- `0x70230`
- `0x146e40`

## string_xrefs

- `0x6fd5c`: `InvalidRemovedStroke`
- `0x6fcf3`: `EmptyScToReplace`
- `0x6fd22`: `EmptyScToReplace`
- `0x6fd06`: `EmptyScToReplaceWith`
- `0x6fd2c`: `strokesToReplace`
- `0x6fd66`: `strokesToReplace`
- `0x6fdaa`: `strokesToReplaceWith`

## pseudocode

```c

```

## disassembly

```asm
0x6fcf0  ldarg.1
0x6fcf1  brtrue.s loc_6FD03
0x6fcf3  ldstr    aEmptysctorepla// "EmptyScToReplace"
0x6fcf8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fcfd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6fd02  throw
0x6fd03  ldarg.2
0x6fd04  brtrue.s loc_6FD16
0x6fd06  ldstr    aEmptysctorepla_0// "EmptyScToReplaceWith"
0x6fd0b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fd10  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6fd15  throw
0x6fd16  ldarg.1
0x6fd17  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Count()
0x6fd1c  stloc.s  6
0x6fd1e  ldloc.s  6
0x6fd20  brtrue.s loc_6FD51
0x6fd22  ldstr    aEmptysctorepla// "EmptyScToReplace"
0x6fd27  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fd2c  ldstr    aStrokestorepla// "strokesToReplace"
0x6fd31  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6fd36  stloc.s  4
0x6fd38  ldloc.s  4
0x6fd3a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x6fd3f  ldstr    aSystemWindowsI_0// "System.Windows.Ink.StrokeCollection"
0x6fd44  ldstr    asc_15E4E4// ""
0x6fd49  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x6fd4e  ldloc.s  4
0x6fd50  throw
0x6fd51  ldarg.0
0x6fd52  ldarg.1
0x6fd53  call     instance int32[] System.Windows.Ink.StrokeCollection::GetStrokeIndexes(class System.Windows.Ink.StrokeCollection strokes)
0x6fd58  stloc.0
0x6fd59  ldloc.0
0x6fd5a  brtrue.s loc_6FD88
0x6fd5c  ldstr    aInvalidremoved// "InvalidRemovedStroke"
0x6fd61  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fd66  ldstr    aStrokestorepla// "strokesToReplace"
0x6fd6b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6fd70  stloc.3
0x6fd71  ldloc.3
0x6fd72  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x6fd77  ldstr    aSystemWindowsI_0// "System.Windows.Ink.StrokeCollection"
0x6fd7c  ldstr    asc_15E4E4// ""
0x6fd81  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x6fd86  ldloc.3
0x6fd87  throw
0x6fd88  ldc.i4.0
0x6fd89  stloc.2
0x6fd8a  br.s     loc_6FDB9
0x6fd8c  ldarg.2
0x6fd8d  ldloc.2
0x6fd8e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Item(!!T0)
0x6fd93  stloc.s  5
0x6fd95  ldarg.0
0x6fd96  ldloc.s  5
0x6fd98  call     instance int32 System.Windows.Ink.StrokeCollection::IndexOf(class System.Windows.Ink.Stroke stroke)
0x6fd9d  ldc.i4.m1
0x6fd9e  beq.s    loc_6FDB5
0x6fda0  ldstr    aStrokeisduplic// "StrokeIsDuplicated"
0x6fda5  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fdaa  ldstr    aStrokestorepla_0// "strokesToReplaceWith"
0x6fdaf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6fdb4  throw
0x6fdb5  ldloc.2
0x6fdb6  ldc.i4.1
0x6fdb7  add
0x6fdb8  stloc.2
0x6fdb9  ldloc.2
0x6fdba  ldarg.2
0x6fdbb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Count()
0x6fdc0  blt.s    loc_6FD8C
0x6fdc2  ldloc.0
0x6fdc3  ldlen
0x6fdc4  conv.i4
0x6fdc5  ldc.i4.1
0x6fdc6  sub
0x6fdc7  stloc.1
0x6fdc8  br.s     loc_6FDE1
0x6fdca  ldarg.0
0x6fdcb  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Items()
0x6fdd0  castclass class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>
0x6fdd5  ldloc.0
0x6fdd6  ldloc.1
0x6fdd7  ldelem.i4
0x6fdd8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>::RemoveAt(int32)
0x6fddd  ldloc.1
0x6fdde  ldc.i4.1
0x6fddf  sub
0x6fde0  stloc.1
0x6fde1  ldloc.1
0x6fde2  ldc.i4.0
0x6fde3  bge.s    loc_6FDCA
0x6fde5  ldarg.2
0x6fde6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Count()
0x6fdeb  ldc.i4.0
0x6fdec  ble.s    loc_6FE02
0x6fdee  ldarg.0
0x6fdef  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Items()
0x6fdf4  castclass class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>
0x6fdf9  ldloc.0
0x6fdfa  ldc.i4.0
0x6fdfb  ldelem.i4
0x6fdfc  ldarg.2
0x6fdfd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>::InsertRange(int32, class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6fe02  ldarg.0
0x6fe03  ldarg.2
0x6fe04  ldarg.1
0x6fe05  ldloc.0
0x6fe06  ldc.i4.0
0x6fe07  ldelem.i4
0x6fe08  call     instance void System.Windows.Ink.StrokeCollection::RaiseStrokesChanged(class System.Windows.Ink.StrokeCollection addedStrokes, class System.Windows.Ink.StrokeCollection removedStrokes, int32 index)
0x6fe0d  ret
```
