# System.Windows.Ink.StrokeCollection::Remove

- ea: `0x6fbc0`
- end: `0x6fc3d`
- name: `System.Windows.Ink.StrokeCollection::Remove`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x6fbc0`
- `0x70170`
- `0x70230`
- `0x146e40`

## string_xrefs

- `0x6fbe2`: `InvalidRemovedStroke`

## pseudocode

```c

```

## disassembly

```asm
0x6fbc0  ldarg.1
0x6fbc1  brtrue.s loc_6FBCE
0x6fbc3  ldstr    aStrokes// "strokes"
0x6fbc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6fbcd  throw
0x6fbce  ldarg.1
0x6fbcf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Count()
0x6fbd4  brtrue.s loc_6FBD7
0x6fbd6  ret
0x6fbd7  ldarg.0
0x6fbd8  ldarg.1
0x6fbd9  call     instance int32[] System.Windows.Ink.StrokeCollection::GetStrokeIndexes(class System.Windows.Ink.StrokeCollection strokes)
0x6fbde  stloc.1
0x6fbdf  ldloc.1
0x6fbe0  brtrue.s loc_6FC0E
0x6fbe2  ldstr    aInvalidremoved// "InvalidRemovedStroke"
0x6fbe7  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6fbec  ldstr    aStrokes// "strokes"
0x6fbf1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6fbf6  stloc.2
0x6fbf7  ldloc.2
0x6fbf8  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x6fbfd  ldstr    aSystemWindowsI_0// "System.Windows.Ink.StrokeCollection"
0x6fc02  ldstr    asc_15E4E4// ""
0x6fc07  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x6fc0c  ldloc.2
0x6fc0d  throw
0x6fc0e  ldloc.1
0x6fc0f  ldlen
0x6fc10  conv.i4
0x6fc11  ldc.i4.1
0x6fc12  sub
0x6fc13  stloc.0
0x6fc14  br.s     loc_6FC2D
0x6fc16  ldarg.0
0x6fc17  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Ink.Stroke>::get_Items()
0x6fc1c  castclass class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>
0x6fc21  ldloc.1
0x6fc22  ldloc.0
0x6fc23  ldelem.i4
0x6fc24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Ink.Stroke>::RemoveAt(int32)
0x6fc29  ldloc.0
0x6fc2a  ldc.i4.1
0x6fc2b  sub
0x6fc2c  stloc.0
0x6fc2d  ldloc.0
0x6fc2e  ldc.i4.0
0x6fc2f  bge.s    loc_6FC16
0x6fc31  ldarg.0
0x6fc32  ldnull
0x6fc33  ldarg.1
0x6fc34  ldloc.1
0x6fc35  ldc.i4.0
0x6fc36  ldelem.i4
0x6fc37  call     instance void System.Windows.Ink.StrokeCollection::RaiseStrokesChanged(class System.Windows.Ink.StrokeCollection addedStrokes, class System.Windows.Ink.StrokeCollection removedStrokes, int32 index)
0x6fc3c  ret
```
