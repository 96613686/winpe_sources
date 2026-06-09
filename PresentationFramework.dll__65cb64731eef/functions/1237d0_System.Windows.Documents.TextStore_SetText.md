# System.Windows.Documents.TextStore::SetText

- ea: `0x1237d0`
- end: `0x123961`
- name: `System.Windows.Documents.TextStore::SetText`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x38c40`
- `0xe41b0`
- `0xe41f0`
- `0xe42c0`
- `0x104e20`
- `0x113fd0`
- `0x115130`
- `0x1237d0`
- `0x126160`
- `0x126290`
- `0x126330`
- `0x1263b0`
- `0x126550`
- `0x126730`
- `0x126ea0`
- `0x126ec0`
- `0x126f10`
- `0x26c4f0`

## string_xrefs

- `0x1237d8`: `TextStore_TS_E_READONLY`
- `0x123858`: `TextStore_CompositionRejected`
- `0x123891`: `TextStore_CompositionRejected`

## pseudocode

```c

```

## disassembly

```asm
0x1237d0  ldarg.0
0x1237d1  call     instance bool System.Windows.Documents.TextStore::get_IsReadOnly()
0x1237d6  brfalse.s loc_1237ED
0x1237d8  ldstr    aTextstoreTsERe// "TextStore_TS_E_READONLY"
0x1237dd  call     string System.Windows.SR::Get(string id)
0x1237e2  ldc.i4   0x80040209
0x1237e7  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x1237ec  throw
0x1237ed  ldarg.0
0x1237ee  call     instance bool System.Windows.Documents.TextStore::get_IsTracing()
0x1237f3  brfalse.s loc_123834
0x1237f5  ldarg.0
0x1237f6  ldc.i4.s 0xB
0x1237f8  ldc.i4.5
0x1237f9  newarr   [mscorlib]System.Object
0x1237fe  dup
0x1237ff  ldc.i4.0
0x123800  ldstr    aText_2// "text:"
0x123805  stelem.ref
0x123806  dup
0x123807  ldc.i4.1
0x123808  ldarg.2
0x123809  box      [mscorlib]System.Int32
0x12380e  stelem.ref
0x12380f  dup
0x123810  ldc.i4.2
0x123811  ldarg.3
0x123812  box      [mscorlib]System.Int32
0x123817  stelem.ref
0x123818  dup
0x123819  ldc.i4.3
0x12381a  ldarg.s  5
0x12381c  box      [mscorlib]System.Int32
0x123821  stelem.ref
0x123822  dup
0x123823  ldc.i4.4
0x123824  ldarg.s  4
0x123826  ldc.i4.0
0x123827  ldarg.s  5
0x123829  newobj   instance void [mscorlib]System.String::.ctor(char[], int32, int32)
0x12382e  stelem.ref
0x12382f  call     void IMECompositionTracer::Trace(class System.Windows.Documents.TextStore textStore, valuetype IMECompositionTraceOp op, object[] args)
0x123834  ldarg.0
0x123835  ldarg.2
0x123836  ldarg.3
0x123837  ldloca.s 0
0x123839  ldloca.s 1
0x12383b  call     instance void System.Windows.Documents.TextStore::GetNormalizedRange(int32 startCharOffset, int32 endCharOffset, [out] class System.Windows.Documents.ITextPointer& start, [out] class System.Windows.Documents.ITextPointer& end)
0x123840  br.s     loc_12384A
0x123842  ldloc.0
0x123843  ldc.i4.1
0x123844  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextPointer::GetNextInsertionPosition(valuetype System.Windows.Documents.LogicalDirection direction)
0x123849  stloc.0
0x12384a  ldloc.0
0x12384b  brfalse.s loc_123855
0x12384d  ldloc.0
0x12384e  call     bool System.Windows.Documents.TextPointerBase::IsBeforeFirstTable(class System.Windows.Documents.ITextPointer position)
0x123853  brtrue.s loc_123842
0x123855  ldloc.0
0x123856  brtrue.s loc_12386D
0x123858  ldstr    aTextstoreCompo// "TextStore_CompositionRejected"
0x12385d  call     string System.Windows.SR::Get(string id)
0x123862  ldc.i4   0x80004005
0x123867  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x12386c  throw
0x12386d  ldloc.0
0x12386e  ldloc.1
0x12386f  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x123874  ldc.i4.0
0x123875  ble.s    loc_123879
0x123877  ldloc.0
0x123878  stloc.1
0x123879  ldarg.0
0x12387a  ldarg.s  4
0x12387c  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x123881  ldloc.0
0x123882  ldloc.1
0x123883  callvirt instance int32 System.Windows.Documents.ITextPointer::GetOffsetToPosition(class System.Windows.Documents.ITextPointer position)
0x123888  call     instance string System.Windows.Documents.TextStore::FilterCompositionString(string text, int32 charsToReplaceCount)
0x12388d  stloc.2
0x12388e  ldloc.2
0x12388f  brtrue.s loc_1238A6
0x123891  ldstr    aTextstoreCompo// "TextStore_CompositionRejected"
0x123896  call     string System.Windows.SR::Get(string id)
0x12389b  ldc.i4   0x80004005
0x1238a0  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x1238a5  throw
0x1238a6  ldarg.0
0x1238a7  call     instance class CompositionParentUndoUnit System.Windows.Documents.TextStore::OpenCompositionUndoUnit()
0x1238ac  stloc.3
0x1238ad  ldc.i4.1
0x1238ae  stloc.s  4
0x1238b0  ldloc.0
0x1238b1  ldloc.1
0x1238b2  ldc.i4.1
0x1238b3  newobj   instance void System.Windows.Documents.TextRange::.ctor(class System.Windows.Documents.ITextPointer position1, class System.Windows.Documents.ITextPointer position2, bool ignoreTextUnitBoundaries)
0x1238b8  stloc.s  5
0x1238ba  ldarg.0
0x1238bb  call     instance class System.Windows.Documents.TextEditor System.Windows.Documents.TextStore::get_TextEditor()
0x1238c0  ldloc.s  5
0x1238c2  ldloc.2
0x1238c3  call     class [PresentationCore]System.Windows.Input.InputLanguageManager [PresentationCore]System.Windows.Input.InputLanguageManager::get_Current()
0x1238c8  callvirt instance class [mscorlib]System.Globalization.CultureInfo [PresentationCore]System.Windows.Input.InputLanguageManager::get_CurrentInputLanguage()
0x1238cd  callvirt instance void System.Windows.Documents.TextEditor::SetText(class System.Windows.Documents.ITextRange range, string text, class [mscorlib]System.Globalization.CultureInfo cultureInfo)
0x1238d2  ldarg.s  6
0x1238d4  ldarg.2
0x1238d5  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::start
0x1238da  ldarg.s  6
0x1238dc  ldarg.3
0x1238dd  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::oldEnd
0x1238e2  ldarg.s  6
0x1238e4  ldarg.3
0x1238e5  ldarg.s  4
0x1238e7  ldlen
0x1238e8  conv.i4
0x1238e9  add
0x1238ea  ldarg.3
0x1238eb  ldarg.2
0x1238ec  sub
0x1238ed  sub
0x1238ee  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::newEnd
0x1238f3  ldarg.0
0x1238f4  ldarg.s  6
0x1238f6  ldobj    [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE
0x1238fb  call     instance void System.Windows.Documents.TextStore::ValidateChange(valuetype [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE change)
0x123900  ldarg.0
0x123901  call     instance void System.Windows.Documents.TextStore::VerifyTextStoreConsistency()
0x123906  ldc.i4.0
0x123907  stloc.s  4
0x123909  leave.s  loc_123915
0x12390b  ldarg.0
0x12390c  ldloc.3
0x12390d  ldloc.s  4
0x12390f  call     instance void System.Windows.Documents.TextStore::CloseTextParentUndoUnit(class System.Windows.Documents.TextParentUndoUnit textParentUndoUnit, valuetype MS.Internal.Documents.UndoCloseAction undoCloseAction)
0x123914  endfinally
0x123915  ldarg.0
0x123916  call     instance bool System.Windows.Documents.TextStore::get_IsTracing()
0x12391b  brfalse.s loc_123960
0x12391d  ldarg.0
0x12391e  ldc.i4.s 0x22
0x123920  ldc.i4.4
0x123921  newarr   [mscorlib]System.Object
0x123926  dup
0x123927  ldc.i4.0
0x123928  ldstr    aChange// "change:"
0x12392d  stelem.ref
0x12392e  dup
0x12392f  ldc.i4.1
0x123930  ldarg.s  6
0x123932  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::start
0x123937  box      [mscorlib]System.Int32
0x12393c  stelem.ref
0x12393d  dup
0x12393e  ldc.i4.2
0x12393f  ldarg.s  6
0x123941  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::oldEnd
0x123946  box      [mscorlib]System.Int32
0x12394b  stelem.ref
0x12394c  dup
0x12394d  ldc.i4.3
0x12394e  ldarg.s  6
0x123950  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::newEnd
0x123955  box      [mscorlib]System.Int32
0x12395a  stelem.ref
0x12395b  call     void IMECompositionTracer::Trace(class System.Windows.Documents.TextStore textStore, valuetype IMECompositionTraceOp op, object[] args)
0x123960  ret
```
