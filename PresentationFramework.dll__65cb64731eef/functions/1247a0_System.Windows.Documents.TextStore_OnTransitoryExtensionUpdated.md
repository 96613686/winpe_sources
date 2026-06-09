# System.Windows.Documents.TextStore::OnTransitoryExtensionUpdated

- ea: `0x1247a0`
- end: `0x1248dc`
- name: `System.Windows.Documents.TextStore::OnTransitoryExtensionUpdated`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x38c40`
- `0xe4150`
- `0xe41e0`
- `0xe41f0`
- `0xe4220`
- `0xe4280`
- `0xe4450`
- `0xe4560`
- `0xe4570`
- `0xe4580`
- `0xe4720`
- `0x104e20`
- `0x105450`
- `0x1057c0`
- `0x1247a0`
- `0x125f20`
- `0x126290`
- `0x126ea0`
- `0x126eb0`

## string_xrefs

- `0x124889`: `TextStore_CompositionRejected`

## pseudocode

```c

```

## disassembly

```asm
0x1247a0  ldarg.s  5
0x1247a2  ldc.i4.1
0x1247a3  stind.i1
0x1247a4  ldarg.3
0x1247a5  brfalse  loc_1248DB
0x1247aa  ldarg.3
0x1247ab  ldarg.2
0x1247ac  call     string System.Windows.Documents.TextStore::StringFromITfRange(class [WindowsBase]MS.Win32.UnsafeNativeMethods/ITfRange range, int32 ecReadOnly)
0x1247b1  stloc.0
0x1247b2  ldloc.0
0x1247b3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1247b8  ldc.i4.0
0x1247b9  ble      loc_1248DB
0x1247be  ldarg.0
0x1247bf  call     instance class System.Windows.Documents.TextEditor System.Windows.Documents.TextStore::get_TextEditor()
0x1247c4  callvirt instance bool System.Windows.Documents.TextEditor::get_AllowOvertype()
0x1247c9  brfalse  loc_124863
0x1247ce  ldarg.0
0x1247cf  call     instance class System.Windows.Documents.TextEditor System.Windows.Documents.TextStore::get_TextEditor()
0x1247d4  callvirt instance bool System.Windows.Documents.TextEditor::get__OvertypeMode()
0x1247d9  brfalse  loc_124863
0x1247de  ldarg.0
0x1247df  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1247e4  callvirt instance bool System.Windows.Documents.ITextRange::get_IsEmpty()
0x1247e9  brfalse.s loc_124863
0x1247eb  ldarg.0
0x1247ec  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1247f1  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x1247f6  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextPointer::CreatePointer()
0x1247fb  stloc.2
0x1247fc  ldloc.2
0x1247fd  ldc.i4.1
0x1247fe  callvirt instance bool System.Windows.Documents.ITextPointer::MoveToInsertionPosition(valuetype System.Windows.Documents.LogicalDirection direction)
0x124803  pop
0x124804  ldloc.2
0x124805  ldc.i4.1
0x124806  callvirt instance valuetype System.Windows.Documents.TextPointerContext System.Windows.Documents.ITextPointer::GetPointerContext(valuetype System.Windows.Documents.LogicalDirection direction)
0x12480b  ldc.i4.1
0x12480c  bne.un.s loc_124863
0x12480e  ldc.i4.2
0x12480f  newarr   [mscorlib]System.Char
0x124814  stloc.3
0x124815  ldloc.2
0x124816  ldc.i4.1
0x124817  ldloc.3
0x124818  ldc.i4.0
0x124819  ldloc.3
0x12481a  ldlen
0x12481b  conv.i4
0x12481c  callvirt instance int32 System.Windows.Documents.ITextPointer::GetTextInRun(valuetype System.Windows.Documents.LogicalDirection direction, char[] textBuffer, int32 startIndex, int32 count)
0x124821  pop
0x124822  ldloc.3
0x124823  ldc.i4.0
0x124824  ldelem.u2
0x124825  call     string [mscorlib]System.Environment::get_NewLine()
0x12482a  ldc.i4.0
0x12482b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x124830  bne.un.s loc_124842
0x124832  ldloc.3
0x124833  ldc.i4.1
0x124834  ldelem.u2
0x124835  call     string [mscorlib]System.Environment::get_NewLine()
0x12483a  ldc.i4.1
0x12483b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x124840  beq.s    loc_124863
0x124842  ldloc.0
0x124843  callvirt instance int32 [mscorlib]System.String::get_Length()
0x124848  stloc.s  4
0x12484a  br.s     loc_124859
0x12484c  ldarg.0
0x12484d  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x124852  ldc.i4.1
0x124853  callvirt instance bool System.Windows.Documents.ITextSelection::ExtendToNextInsertionPosition(valuetype System.Windows.Documents.LogicalDirection direction)
0x124858  pop
0x124859  ldloc.s  4
0x12485b  dup
0x12485c  ldc.i4.1
0x12485d  sub
0x12485e  stloc.s  4
0x124860  ldc.i4.0
0x124861  bgt.s    loc_12484C
0x124863  ldarg.0
0x124864  ldloc.0
0x124865  ldarg.0
0x124866  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x12486b  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_Start()
0x124870  ldarg.0
0x124871  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x124876  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x12487b  callvirt instance int32 System.Windows.Documents.ITextPointer::GetOffsetToPosition(class System.Windows.Documents.ITextPointer position)
0x124880  call     instance string System.Windows.Documents.TextStore::FilterCompositionString(string text, int32 charsToReplaceCount)
0x124885  stloc.1
0x124886  ldloc.1
0x124887  brtrue.s loc_12489E
0x124889  ldstr    aTextstoreCompo// "TextStore_CompositionRejected"
0x12488e  call     string System.Windows.SR::Get(string id)
0x124893  ldc.i4   0x80004005
0x124898  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x12489d  throw
0x12489e  ldarg.0
0x12489f  call     instance class System.Windows.Documents.TextEditor System.Windows.Documents.TextStore::get_TextEditor()
0x1248a4  ldarg.0
0x1248a5  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1248aa  ldloc.1
0x1248ab  call     class [PresentationCore]System.Windows.Input.InputLanguageManager [PresentationCore]System.Windows.Input.InputLanguageManager::get_Current()
0x1248b0  callvirt instance class [mscorlib]System.Globalization.CultureInfo [PresentationCore]System.Windows.Input.InputLanguageManager::get_CurrentInputLanguage()
0x1248b5  callvirt instance void System.Windows.Documents.TextEditor::SetText(class System.Windows.Documents.ITextRange range, string text, class [mscorlib]System.Globalization.CultureInfo cultureInfo)
0x1248ba  ldarg.0
0x1248bb  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1248c0  ldarg.0
0x1248c1  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1248c6  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x1248cb  ldarg.0
0x1248cc  call     instance class System.Windows.Documents.ITextSelection System.Windows.Documents.TextStore::get_TextSelection()
0x1248d1  callvirt instance class System.Windows.Documents.ITextPointer System.Windows.Documents.ITextRange::get_End()
0x1248d6  callvirt instance void System.Windows.Documents.ITextRange::Select(class System.Windows.Documents.ITextPointer position1, class System.Windows.Documents.ITextPointer position2)
0x1248db  ret
```
