# System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent

- ea: `0xc140`
- end: `0xc1f8`
- name: `System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xbd50`
- `0xc140`
- `0xc200`

## pseudocode

```c

```

## disassembly

```asm
0xc140  ldarg.0
0xc141  ldarg.2
0xc142  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs::get_WritingLevel()
0xc147  call     instance valuetype [PresentationFramework]System.Windows.Documents.Serialization.WritingProgressChangeLevel System.Windows.Xps.XpsDocumentWriter::TranslateProgressChangeLevel(valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel xpsChangeLevel)
0xc14c  ldarg.0
0xc14d  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc152  ldarg.2
0xc153  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs::get_WritingLevel()
0xc158  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc15d  unbox    [mscorlib]System.Int32
0xc162  ldind.i4
0xc163  ldarg.2
0xc164  call     instance int32 [System]System.ComponentModel.ProgressChangedEventArgs::get_ProgressPercentage()
0xc169  ldarg.0
0xc16a  ldfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xc16f  newobj   instance void [PresentationFramework]System.Windows.Documents.Serialization.WritingProgressChangedEventArgs::.ctor(valuetype [PresentationFramework]System.Windows.Documents.Serialization.WritingProgressChangeLevel, int32, int32, object)
0xc174  stloc.0
0xc175  ldarg.2
0xc176  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs::get_WritingLevel()
0xc17b  stloc.1
0xc17c  ldloca.s 1
0xc17e  ldind.i4
0xc17f  ldc.i4.1
0xc180  beq.s    loc_C19C
0xc182  ldloca.s 1
0xc184  ldind.i4
0xc185  ldc.i4.2
0xc186  bne.un.s loc_C1C0
0xc188  ldarg.0
0xc189  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc18e  ldc.i4.3
0xc18f  ldc.i4.1
0xc190  box      [mscorlib]System.Int32
0xc195  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc19a  br.s     loc_C1C0
0xc19c  ldarg.0
0xc19d  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc1a2  ldc.i4.2
0xc1a3  ldc.i4.1
0xc1a4  box      [mscorlib]System.Int32
0xc1a9  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc1ae  ldarg.0
0xc1af  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc1b4  ldc.i4.3
0xc1b5  ldc.i4.1
0xc1b6  box      [mscorlib]System.Int32
0xc1bb  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc1c0  ldarg.0
0xc1c1  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc1c6  ldarg.2
0xc1c7  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs::get_WritingLevel()
0xc1cc  ldarg.0
0xc1cd  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc1d2  ldarg.2
0xc1d3  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.XpsWritingProgressChangeLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs::get_WritingLevel()
0xc1d8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc1dd  unbox    [mscorlib]System.Int32
0xc1e2  ldind.i4
0xc1e3  ldc.i4.1
0xc1e4  add
0xc1e5  box      [mscorlib]System.Int32
0xc1ea  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc1ef  ldarg.0
0xc1f0  dup
0xc1f1  ldloc.0
0xc1f2  callvirt instance void System.Windows.Xps.XpsDocumentWriter::raise_WritingProgressChanged(object sender, class [PresentationFramework]System.Windows.Documents.Serialization.WritingProgressChangedEventArgs e)
0xc1f7  ret
```
