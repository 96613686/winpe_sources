# System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled

- ea: `0xc660`
- end: `0xc683`
- name: `System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0xc6e0`
- `0xc970`
- `0xc9f0`
- `0xd330`

## callees

- `0xbde0`
- `0xc660`

## pseudocode

```c

```

## disassembly

```asm
0xc660  ldarg.0
0xc661  ldfld    int32 System.Windows.Xps.XpsDocumentWriter::_writingCancelledEventHandlersCount
0xc666  ldc.i4.0
0xc667  ble.s    loc_C678
0xc669  ldarg.2
0xc66a  newobj   instance void [PresentationFramework]System.Windows.Documents.Serialization.WritingCancelledEventArgs::.ctor(class [mscorlib]System.Exception)
0xc66f  stloc.0
0xc670  ldarg.0
0xc671  ldarg.1
0xc672  ldloc.0
0xc673  callvirt instance void System.Windows.Xps.XpsDocumentWriter::raise_WritingCancelled(object sender, class [PresentationFramework]System.Windows.Documents.Serialization.WritingCancelledEventArgs args)
0xc678  ldarg.0
0xc679  ldfld    int32 System.Windows.Xps.XpsDocumentWriter::_writingCancelledEventHandlersCount
0xc67e  ldc.i4.0
0xc67f  cgt
0xc681  conv.u1
0xc682  ret
```
