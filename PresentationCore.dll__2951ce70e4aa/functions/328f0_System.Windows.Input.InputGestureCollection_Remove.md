# System.Windows.Input.InputGestureCollection::Remove

- ea: `0x328f0`
- end: `0x3293a`
- name: `System.Windows.Input.InputGestureCollection::Remove`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x32620`

## callees

- `0x328e0`
- `0x328f0`
- `0x146e40`

## string_xrefs

- `0x328f8`: `ReadOnlyInputGesturesCollection`

## pseudocode

```c

```

## disassembly

```asm
0x328f0  ldarg.0
0x328f1  call     instance bool System.Windows.Input.InputGestureCollection::get_IsReadOnly()
0x328f6  brfalse.s loc_32908
0x328f8  ldstr    aReadonlyinputg// "ReadOnlyInputGesturesCollection"
0x328fd  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x32902  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x32907  throw
0x32908  ldarg.1
0x32909  brtrue.s loc_32916
0x3290b  ldstr    aInputgesture// "inputGesture"
0x32910  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32915  throw
0x32916  ldarg.0
0x32917  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.InputGesture> System.Windows.Input.InputGestureCollection::_innerGestureList
0x3291c  brfalse.s loc_32939
0x3291e  ldarg.0
0x3291f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.InputGesture> System.Windows.Input.InputGestureCollection::_innerGestureList
0x32924  ldarg.1
0x32925  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.InputGesture>::Contains(var<u1>)
0x3292a  brfalse.s loc_32939
0x3292c  ldarg.0
0x3292d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.InputGesture> System.Windows.Input.InputGestureCollection::_innerGestureList
0x32932  ldarg.1
0x32933  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.InputGesture>::Remove(var<u1>)
0x32938  pop
0x32939  ret
```
