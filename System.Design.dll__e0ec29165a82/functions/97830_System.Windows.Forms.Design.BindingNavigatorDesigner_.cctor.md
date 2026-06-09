# System.Windows.Forms.Design.BindingNavigatorDesigner::.cctor

- ea: `0x97830`
- end: `0x9787c`
- name: `System.Windows.Forms.Design.BindingNavigatorDesigner::.cctor`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x97838`: `MovePreviousItem`
- `0x97840`: `MoveFirstItem`
- `0x97848`: `MoveNextItem`
- `0x97850`: `MoveLastItem`
- `0x97860`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x97830  ldc.i4.8
0x97831  newarr   [mscorlib]System.String
0x97836  dup
0x97837  ldc.i4.0
0x97838  ldstr    aMovepreviousit// "MovePreviousItem"
0x9783d  stelem.ref
0x9783e  dup
0x9783f  ldc.i4.1
0x97840  ldstr    aMovefirstitem// "MoveFirstItem"
0x97845  stelem.ref
0x97846  dup
0x97847  ldc.i4.2
0x97848  ldstr    aMovenextitem// "MoveNextItem"
0x9784d  stelem.ref
0x9784e  dup
0x9784f  ldc.i4.3
0x97850  ldstr    aMovelastitem// "MoveLastItem"
0x97855  stelem.ref
0x97856  dup
0x97857  ldc.i4.4
0x97858  ldstr    aAddnewitem// "AddNewItem"
0x9785d  stelem.ref
0x9785e  dup
0x9785f  ldc.i4.5
0x97860  ldstr    aDeleteitem// "DeleteItem"
0x97865  stelem.ref
0x97866  dup
0x97867  ldc.i4.6
0x97868  ldstr    aPositionitem// "PositionItem"
0x9786d  stelem.ref
0x9786e  dup
0x9786f  ldc.i4.7
0x97870  ldstr    aCountitem// "CountItem"
0x97875  stelem.ref
0x97876  stsfld   string[] System.Windows.Forms.Design.BindingNavigatorDesigner::itemNames
0x9787b  ret
```
