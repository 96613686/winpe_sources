# System.Windows.Forms.Design.SelectionUIService::GetTransactionName

- ea: `0xc6240`
- end: `0xc6361`
- name: `System.Windows.Forms.Design.SelectionUIService::GetTransactionName`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xc6f70`

## callees

- `0x8eec0`
- `0xc6240`

## string_xrefs

- `0xc624f`: `DragDropMoveComponents`
- `0xc62aa`: `DragDropMoveComponent`
- `0xc62d0`: `DragDropSizeComponents`
- `0xc632c`: `DragDropSizeComponent`
- `0xc6343`: `DragDropDragComponents`

## pseudocode

```c

```

## disassembly

```asm
0xc6240  ldarg.0
0xc6241  ldc.i4   0x10000000
0xc6246  and
0xc6247  brfalse.s loc_C62C4
0xc6249  ldarg.1
0xc624a  ldlen
0xc624b  conv.i4
0xc624c  ldc.i4.1
0xc624d  ble.s    loc_C6270
0xc624f  ldstr    aDragdropmoveco// "DragDropMoveComponents"
0xc6254  ldc.i4.1
0xc6255  newarr   [mscorlib]System.Object
0xc625a  dup
0xc625b  ldc.i4.0
0xc625c  ldarg.1
0xc625d  ldlen
0xc625e  conv.i4
0xc625f  box      [mscorlib]System.Int32
0xc6264  stelem.ref
0xc6265  call     string System.Design.SR::GetString(string name, object[] args)
0xc626a  stloc.0
0xc626b  br       loc_C635F
0xc6270  ldsfld   string [mscorlib]System.String::Empty
0xc6275  stloc.1
0xc6276  ldarg.1
0xc6277  ldlen
0xc6278  brfalse.s loc_C62AA
0xc627a  ldarg.1
0xc627b  ldc.i4.0
0xc627c  ldelem.ref
0xc627d  isinst   [System]System.ComponentModel.IComponent
0xc6282  stloc.2
0xc6283  ldloc.2
0xc6284  brfalse.s loc_C629C
0xc6286  ldloc.2
0xc6287  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc628c  brfalse.s loc_C629C
0xc628e  ldloc.2
0xc628f  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc6294  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xc6299  stloc.1
0xc629a  br.s     loc_C62AA
0xc629c  ldarg.1
0xc629d  ldc.i4.0
0xc629e  ldelem.ref
0xc629f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc62a4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xc62a9  stloc.1
0xc62aa  ldstr    aDragdropmoveco_0// "DragDropMoveComponent"
0xc62af  ldc.i4.1
0xc62b0  newarr   [mscorlib]System.Object
0xc62b5  dup
0xc62b6  ldc.i4.0
0xc62b7  ldloc.1
0xc62b8  stelem.ref
0xc62b9  call     string System.Design.SR::GetString(string name, object[] args)
0xc62be  stloc.0
0xc62bf  br       loc_C635F
0xc62c4  ldarg.0
0xc62c5  ldc.i4.s 0xF
0xc62c7  and
0xc62c8  brfalse.s loc_C6343
0xc62ca  ldarg.1
0xc62cb  ldlen
0xc62cc  conv.i4
0xc62cd  ldc.i4.1
0xc62ce  ble.s    loc_C62EE
0xc62d0  ldstr    aDragdropsizeco// "DragDropSizeComponents"
0xc62d5  ldc.i4.1
0xc62d6  newarr   [mscorlib]System.Object
0xc62db  dup
0xc62dc  ldc.i4.0
0xc62dd  ldarg.1
0xc62de  ldlen
0xc62df  conv.i4
0xc62e0  box      [mscorlib]System.Int32
0xc62e5  stelem.ref
0xc62e6  call     string System.Design.SR::GetString(string name, object[] args)
0xc62eb  stloc.0
0xc62ec  br.s     loc_C635F
0xc62ee  ldsfld   string [mscorlib]System.String::Empty
0xc62f3  stloc.3
0xc62f4  ldarg.1
0xc62f5  ldlen
0xc62f6  brfalse.s loc_C632C
0xc62f8  ldarg.1
0xc62f9  ldc.i4.0
0xc62fa  ldelem.ref
0xc62fb  isinst   [System]System.ComponentModel.IComponent
0xc6300  stloc.s  4
0xc6302  ldloc.s  4
0xc6304  brfalse.s loc_C631E
0xc6306  ldloc.s  4
0xc6308  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc630d  brfalse.s loc_C631E
0xc630f  ldloc.s  4
0xc6311  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc6316  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xc631b  stloc.3
0xc631c  br.s     loc_C632C
0xc631e  ldarg.1
0xc631f  ldc.i4.0
0xc6320  ldelem.ref
0xc6321  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc6326  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xc632b  stloc.3
0xc632c  ldstr    aDragdropsizeco_0// "DragDropSizeComponent"
0xc6331  ldc.i4.1
0xc6332  newarr   [mscorlib]System.Object
0xc6337  dup
0xc6338  ldc.i4.0
0xc6339  ldloc.3
0xc633a  stelem.ref
0xc633b  call     string System.Design.SR::GetString(string name, object[] args)
0xc6340  stloc.0
0xc6341  br.s     loc_C635F
0xc6343  ldstr    aDragdropdragco// "DragDropDragComponents"
0xc6348  ldc.i4.1
0xc6349  newarr   [mscorlib]System.Object
0xc634e  dup
0xc634f  ldc.i4.0
0xc6350  ldarg.1
0xc6351  ldlen
0xc6352  conv.i4
0xc6353  box      [mscorlib]System.Int32
0xc6358  stelem.ref
0xc6359  call     string System.Design.SR::GetString(string name, object[] args)
0xc635e  stloc.0
0xc635f  ldloc.0
0xc6360  ret
```
