# System.Windows.Input.InputGestureCollection::System.Collections.IList.Remove

- ea: `0x32620`
- end: `0x32645`
- name: `System.Windows.Input.InputGestureCollection::System.Collections.IList.Remove`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x32620`
- `0x328e0`
- `0x328f0`
- `0x146e40`

## string_xrefs

- `0x32628`: `ReadOnlyInputGesturesCollection`

## pseudocode

```c

```

## disassembly

```asm
0x32620  ldarg.0
0x32621  call     instance bool System.Windows.Input.InputGestureCollection::get_IsReadOnly()
0x32626  brfalse.s loc_32638
0x32628  ldstr    aReadonlyinputg// "ReadOnlyInputGesturesCollection"
0x3262d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x32632  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x32637  throw
0x32638  ldarg.0
0x32639  ldarg.1
0x3263a  isinst   System.Windows.Input.InputGesture
0x3263f  call     instance void System.Windows.Input.InputGestureCollection::Remove(class System.Windows.Input.InputGesture inputGesture)
0x32644  ret
```
