# System.Windows.Documents.TextStore::InsertTextAtSelection

- ea: `0x1239f0`
- end: `0x123c4c`
- name: `System.Windows.Documents.TextStore::InsertTextAtSelection`
- size: `604`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `broker_com_uri`

## callees

- `0x38c40`
- `0xe4150`
- `0xe41a0`
- `0xe41b0`
- `0xe41f0`
- `0xe4400`
- `0xe4410`
- `0xe4450`
- `0xe4480`
- `0xe4560`
- `0xe4570`
- `0xe4820`
- `0xe4830`
- `0x104e40`
- `0x115120`
- `0x1239f0`
- `0x126160`
- `0x126290`
- `0x126330`
- `0x1263b0`
- `0x126440`
- `0x126730`
- `0x126ea0`
- `0x126eb0`
- `0x126ec0`
- `0x126f10`
- `0x26c4f0`

## string_xrefs

- `0x123a18`: `TextStore_TS_E_READONLY`
- `0x123b05`: `TextStore_CompositionRejected`

## pseudocode

```c

```

## disassembly

```asm
0x1239f0  ldarg.s  4
0x1239f2  ldc.i4.m1
0x1239f3  stind.i4
0x1239f4  ldarg.s  5
0x1239f6  ldc.i4.m1
0x1239f7  stind.i4
0x1239f8  ldarg.s  6
0x1239fa  ldc.i4.0
0x1239fb  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::start
0x123a00  ldarg.s  6
0x123a02  ldc.i4.0
0x123a03  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::oldEnd
0x123a08  ldarg.s  6
0x123a0a  ldc.i4.0
0x123a0b  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::newEnd
0x123a10  ldarg.0
0x123a11  call     instance bool System.Windows.Documents.TextStore::get_IsReadOnly()
0x123a16  brfalse.s loc_123A2D
0x123a18  ldstr    aTextstoreTsERe// "TextStore_TS_E_READONLY"
0x123a1d  call     string System.Windows.SR::Get(string id)
0x123a22  ldc.i4   0x80040209
0x123a27  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x123a2c  throw
0x123a2d  ldarg.0
0x123a2e  call     instance bool System.Windows.Documents.TextStore::get_IsTracing()
0x123a33  brfalse.s loc_123A57
0x123a35  ldarg.0
0x123a36  ldc.i4.s 0xC
0x123a38  ldc.i4.2
0x123a39  newarr   [mscorlib]System.Object
0x123a3e  dup
0x123a3f  ldc.i4.0
0x123a40  ldarg.1
0x123a41  box      [WindowsBase]MS.Win32.UnsafeNativeMethods/InsertAtSelectionFlags
0x123a46  stelem.ref
0x123a47  dup
0x123a48  ldc.i4.1
0x123a49  ldarg.2
0x123a4a  ldc.i4.0
0x123a4b  ldarg.3
0x123a4c  newobj   instance void [mscorlib]System.String::.ctor(char[], int32, int32)
0x123a51  stelem.ref
0x123a52  call     void IMECompositionTracer::Trace(class System.Windows.Documents.TextStore textStore, valuetype IMECompositionTraceOp op, object[] args)
0x123a57  ldarg.0
0x123a58  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123a5d  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextSelection::get_AnchorPosition()
0x123a62  ldarg.0
0x123a63  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123a68  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextSelection::get_MovingPosition()
0x123a6d  newobj   instance void System.Windows.Documents.TextRange::.ctor(class System.Windows.Documents.ITextPointer position1, class System.Windows.Documents.ITextPointer position2)
0x123a72  stloc.s  4
0x123a74  ldloc.s  4
0x123a76  ldc.i4.0
0x123a77  callvirt instance void System.Windows.Documents.ITextRange::ApplyTypingHeuristics(bool overType)
0x123a7c  ldloc.s  4
0x123a7e  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_Start()
0x123a83  ldloc.s  4
0x123a85  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x123a8a  ldloca.s 5
0x123a8c  ldloca.s 6
0x123a8e  call     void System.Windows.Documents.TextStore::GetAdjustedSelection(class System.Windows.Documents.ITextPointer startIn, class System.Windows.Documents.ITextPointer endIn, [out] class System.Windows.Documents.ITextPointer& startOut, [out] class System.Windows.Documents.ITextPointer& endOut)
0x123a93  ldloc.s  5
0x123a95  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextPointer::CreatePointer()
0x123a9a  stloc.0
0x123a9b  ldloc.0
0x123a9c  ldc.i4.0
0x123a9d  callvirt instance void System.Windows.Documents.ITextPointer::SetLogicalDirection(valuetype System.Windows.Documents.LogicalDirection direction)
0x123aa2  ldloc.s  6
0x123aa4  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextPointer::CreatePointer()
0x123aa9  stloc.1
0x123aaa  ldloc.1
0x123aab  ldc.i4.1
0x123aac  callvirt instance void System.Windows.Documents.ITextPointer::SetLogicalDirection(valuetype System.Windows.Documents.LogicalDirection direction)
0x123ab1  ldloc.0
0x123ab2  callvirt instance int32 System.Windows.Documents.ITextPointer::get_CharOffset()
0x123ab7  stloc.2
0x123ab8  ldloc.1
0x123ab9  callvirt instance int32 System.Windows.Documents.ITextPointer::get_CharOffset()
0x123abe  stloc.3
0x123abf  ldarg.1
0x123ac0  ldc.i4.2
0x123ac1  and
0x123ac2  brtrue   loc_123BEE
0x123ac7  ldarg.0
0x123ac8  call     instance class CompositionParentUndoUnit System.Windows.Documents.TextStore::OpenCompositionUndoUnit()
0x123acd  stloc.s  7
0x123acf  ldc.i4.1
0x123ad0  stloc.s  8
0x123ad2  ldarg.0
0x123ad3  call     instance void System.Windows.Documents.TextStore::VerifyTextStoreConsistency()
0x123ad8  ldarg.s  6
0x123ada  ldloc.3
0x123adb  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::oldEnd
0x123ae0  ldarg.0
0x123ae1  ldarg.2
0x123ae2  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x123ae7  ldloc.s  4
0x123ae9  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_Start()
0x123aee  ldloc.s  4
0x123af0  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x123af5  callvirt instance int32 System.Windows.Documents.ITextPointer::GetOffsetToPosition(class System.Windows.Documents.ITextPointer position)
0x123afa  call     instance string System.Windows.Documents.TextStore::FilterCompositionString(string text, int32 charsToReplaceCount)
0x123aff  stloc.s  9
0x123b01  ldloc.s  9
0x123b03  brtrue.s loc_123B1A
0x123b05  ldstr    aTextstoreCompo// "TextStore_CompositionRejected"
0x123b0a  call     string System.Windows.SR::Get(string id)
0x123b0f  ldc.i4   0x80004005
0x123b14  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x123b19  throw
0x123b1a  ldarg.0
0x123b1b  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b20  ldc.i4.0
0x123b21  callvirt instance void System.Windows.Documents.ITextRange::ApplyTypingHeuristics(bool overType)
0x123b26  ldloc.s  5
0x123b28  ldarg.0
0x123b29  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b2e  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_Start()
0x123b33  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x123b38  brtrue.s loc_123B4E
0x123b3a  ldloc.s  6
0x123b3c  ldarg.0
0x123b3d  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b42  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x123b47  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x123b4c  brfalse.s loc_123B5D
0x123b4e  ldarg.0
0x123b4f  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b54  ldloc.s  5
0x123b56  ldloc.s  6
0x123b58  callvirt instance void System.Windows.Documents.ITextRange::Select(class System.Windows.Documents.ITextPointer position1, class System.Windows.Documents.ITextPointer position2)
0x123b5d  ldarg.0
0x123b5e  ldfld    bool System.Windows.Documents.TextStore::_isComposing
0x123b63  brtrue.s loc_123B9A
0x123b65  ldarg.0
0x123b66  ldfld    int32 System.Windows.Documents.TextStore::_previousCompositionStartOffset
0x123b6b  ldc.i4.m1
0x123b6c  bne.un.s loc_123B9A
0x123b6e  ldarg.0
0x123b6f  ldarg.0
0x123b70  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b75  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_Start()
0x123b7a  callvirt instance int32 System.Windows.Documents.ITextPointer::get_Offset()
0x123b7f  stfld    int32 System.Windows.Documents.TextStore::_previousCompositionStartOffset
0x123b84  ldarg.0
0x123b85  ldarg.0
0x123b86  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x123b8b  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x123b90  callvirt instance int32 System.Windows.Documents.ITextPointer::get_Offset()
0x123b95  stfld    int32 System.Windows.Documents.TextStore::_previousCompositionEndOffset
0x123b9a  ldarg.0
0x123b9b  call     instance class System.Windows.Documents.TextEditor System.Windows.Documents.TextStore::get_TextEditor()
0x123ba0  ldloc.s  9
0x123ba2  call     class [PresentationCore]System.Windows.Input.InputLanguageManager [PresentationCore]System.Windows.Input.InputLanguageManager::get_Current()
0x123ba7  callvirt instance class [mscorlib]System.Globalization.CultureInfo [PresentationCore]System.Windows.Input.InputLanguageManager::get_CurrentInputLanguage()
0x123bac  callvirt instance void System.Windows.Documents.TextEditor::SetSelectedText(string text, class [mscorlib]System.Globalization.CultureInfo cultureInfo)
0x123bb1  ldarg.s  6
0x123bb3  ldloc.0
0x123bb4  callvirt instance int32 System.Windows.Documents.ITextPointer::get_CharOffset()
0x123bb9  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::start
0x123bbe  ldarg.s  6
0x123bc0  ldloc.1
0x123bc1  callvirt instance int32 System.Windows.Documents.ITextPointer::get_CharOffset()
0x123bc6  stfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::newEnd
0x123bcb  ldarg.0
0x123bcc  ldarg.s  6
0x123bce  ldobj    [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE
0x123bd3  call     instance void System.Windows.Documents.TextStore::ValidateChange(valuetype [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE change)
0x123bd8  ldarg.0
0x123bd9  call     instance void System.Windows.Documents.TextStore::VerifyTextStoreConsistency()
0x123bde  ldc.i4.0
0x123bdf  stloc.s  8
0x123be1  leave.s  loc_123BEE
0x123be3  ldarg.0
0x123be4  ldloc.s  7
0x123be6  ldloc.s  8
0x123be8  call     instance void System.Windows.Documents.TextStore::CloseTextParentUndoUnit(class System.Windows.Documents.TextParentUndoUnit textParentUndoUnit, valuetype MS.Internal.Documents.UndoCloseAction undoCloseAction)
0x123bed  endfinally
0x123bee  ldarg.1
0x123bef  ldc.i4.1
0x123bf0  and
0x123bf1  brtrue.s loc_123C00
0x123bf3  ldarg.s  4
0x123bf5  ldloc.2
0x123bf6  stind.i4
0x123bf7  ldarg.s  5
0x123bf9  ldloc.1
0x123bfa  callvirt instance int32 System.Windows.Documents.ITextPointer::get_CharOffset()
0x123bff  stind.i4
0x123c00  ldarg.0
0x123c01  call     instance bool System.Windows.Documents.TextStore::get_IsTracing()
0x123c06  brfalse.s loc_123C4B
0x123c08  ldarg.0
0x123c09  ldc.i4.s 0x23
0x123c0b  ldc.i4.4
0x123c0c  newarr   [mscorlib]System.Object
0x123c11  dup
0x123c12  ldc.i4.0
0x123c13  ldstr    aChange// "change:"
0x123c18  stelem.ref
0x123c19  dup
0x123c1a  ldc.i4.1
0x123c1b  ldarg.s  6
0x123c1d  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::start
0x123c22  box      [mscorlib]System.Int32
0x123c27  stelem.ref
0x123c28  dup
0x123c29  ldc.i4.2
0x123c2a  ldarg.s  6
0x123c2c  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::oldEnd
0x123c31  box      [mscorlib]System.Int32
0x123c36  stelem.ref
0x123c37  dup
0x123c38  ldc.i4.3
0x123c39  ldarg.s  6
0x123c3b  ldfld    int32 [WindowsBase]MS.Win32.UnsafeNativeMethods/TS_TEXTCHANGE::newEnd
0x123c40  box      [mscorlib]System.Int32
0x123c45  stelem.ref
0x123c46  call     void IMECompositionTracer::Trace(class System.Windows.Documents.TextStore textStore, valuetype IMECompositionTraceOp op, object[] args)
0x123c4b  ret
```
