# System.Windows.Documents.TextRangeEdit::DeleteParagraphContent

- ea: `0x118f20`
- end: `0x1190cc`
- name: `System.Windows.Documents.TextRangeEdit::DeleteParagraphContent`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x118f10`
- `0x11b570`

## callees

- `0xe41b0`
- `0xe4330`
- `0x10e660`
- `0x10e7b0`
- `0x10f5b0`
- `0x1119c0`
- `0x111a10`
- `0x111f80`
- `0x112060`
- `0x112080`
- `0x114620`
- `0x114710`
- `0x117d70`
- `0x118f20`
- `0x1190d0`
- `0x119150`
- `0x119ca0`
- `0x11b220`
- `0x11f470`

## string_xrefs

- `0x119006`: `EnsureInsertionPosition must create a paragraph inside list item - 1`
- `0x119030`: `EnsureInsertionPosition must create a paragraph inside list item - 2`

## pseudocode

```c

```

## disassembly

```asm
0x118f20  ldarg.0
0x118f21  ldnull
0x118f22  cgt.un
0x118f24  ldstr    aNullCheckStart// "null check: start"
0x118f29  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x118f2e  ldarg.1
0x118f2f  ldnull
0x118f30  cgt.un
0x118f32  ldstr    aNullCheckEnd// "null check: end"
0x118f37  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x118f3c  ldarg.0
0x118f3d  ldarg.1
0x118f3e  callvirt instance int32 System.Windows.Documents.ITextPointer::CompareTo(class System.Windows.Documents.ITextPointer position)
0x118f43  ldc.i4.0
0x118f44  cgt
0x118f46  ldc.i4.0
0x118f47  ceq
0x118f49  ldstr    aExpectingStart_1// "expecting: start <= end"
0x118f4e  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x118f53  ldarg.0
0x118f54  isinst   System.Windows.Documents.TextPointer
0x118f59  brtrue.s loc_118F63
0x118f5b  ldarg.0
0x118f5c  ldarg.1
0x118f5d  callvirt instance void System.Windows.Documents.ITextPointer::DeleteContentToPosition(class System.Windows.Documents.ITextPointer limit)
0x118f62  ret
0x118f63  ldarg.0
0x118f64  castclass System.Windows.Documents.TextPointer
0x118f69  stloc.0
0x118f6a  ldarg.1
0x118f6b  castclass System.Windows.Documents.TextPointer
0x118f70  stloc.1
0x118f71  ldloc.0
0x118f72  ldloc.1
0x118f73  call     void System.Windows.Documents.TextRangeEdit::DeleteEquiScopedContent(class System.Windows.Documents.TextPointer start, class System.Windows.Documents.TextPointer end)
0x118f78  ldloc.1
0x118f79  ldloc.0
0x118f7a  call     void System.Windows.Documents.TextRangeEdit::DeleteEquiScopedContent(class System.Windows.Documents.TextPointer start, class System.Windows.Documents.TextPointer end)
0x118f7f  ldloc.0
0x118f80  ldloc.1
0x118f81  callvirt instance int32 System.Windows.Documents.TextPointer::CompareTo(class System.Windows.Documents.TextPointer position)
0x118f86  ldc.i4.0
0x118f87  bge      loc_119053
0x118f8c  ldloc.1
0x118f8d  call     bool System.Windows.Documents.TextPointerBase::IsAfterLastParagraph(class System.Windows.Documents.ITextPointer thisPosition)
0x118f92  brfalse.s loc_118FDA
0x118f94  br.s     loc_118FC1
0x118f96  ldloc.0
0x118f97  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x118f9c  castclass System.Windows.Documents.TextElement
0x118fa1  stloc.2
0x118fa2  ldloc.2
0x118fa3  isinst   System.Windows.Documents.Inline
0x118fa8  brtrue.s loc_118FBA
0x118faa  ldloc.2
0x118fab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x118fb0  call     bool System.Windows.Documents.TextSchema::AllowsParagraphMerging(class [mscorlib]System.Type elementType)
0x118fb5  brfalse  loc_119053
0x118fba  ldloc.2
0x118fbb  ldnull
0x118fbc  callvirt instance void System.Windows.Documents.TextElement::RepositionWithContent(class System.Windows.Documents.TextPointer textPosition)
0x118fc1  ldloc.0
0x118fc2  ldc.i4.0
0x118fc3  callvirt instance valuetype System.Windows.Documents.TextPointerContext System.Windows.Documents.TextPointer::GetPointerContext(valuetype System.Windows.Documents.LogicalDirection direction)
0x118fc8  ldc.i4.3
0x118fc9  bne.un   loc_119053
0x118fce  ldloc.0
0x118fcf  ldc.i4.1
0x118fd0  callvirt instance valuetype System.Windows.Documents.TextPointerContext System.Windows.Documents.TextPointer::GetPointerContext(valuetype System.Windows.Documents.LogicalDirection direction)
0x118fd5  ldc.i4.4
0x118fd6  beq.s    loc_118F96
0x118fd8  br.s     loc_119053
0x118fda  ldloc.0
0x118fdb  callvirt instance class System.Windows.Documents.Block System.Windows.Documents.TextPointer::get_ParagraphOrBlockUIContainer()
0x118fe0  stloc.3
0x118fe1  ldloc.1
0x118fe2  callvirt instance class System.Windows.Documents.Block System.Windows.Documents.TextPointer::get_ParagraphOrBlockUIContainer()
0x118fe7  stloc.s  4
0x118fe9  ldloc.3
0x118fea  brtrue.s loc_119010
0x118fec  ldloc.0
0x118fed  call     bool System.Windows.Documents.TextPointerBase::IsInEmptyListItem(class System.Windows.Documents.TextPointer position)
0x118ff2  brfalse.s loc_119010
0x118ff4  ldloc.0
0x118ff5  call     class System.Windows.Documents.TextPointer System.Windows.Documents.TextRangeEditTables::EnsureInsertionPosition(class System.Windows.Documents.TextPointer position)
0x118ffa  stloc.0
0x118ffb  ldloc.0
0x118ffc  callvirt instance class System.Windows.Documents.Paragraph System.Windows.Documents.TextPointer::get_Paragraph()
0x119001  stloc.3
0x119002  ldloc.3
0x119003  ldnull
0x119004  cgt.un
0x119006  ldstr    aEnsureinsertio_1// "EnsureInsertionPosition must create a p"...
0x11900b  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x119010  ldloc.s  4
0x119012  brtrue.s loc_11903A
0x119014  ldloc.1
0x119015  call     bool System.Windows.Documents.TextPointerBase::IsInEmptyListItem(class System.Windows.Documents.TextPointer position)
0x11901a  brfalse.s loc_11903A
0x11901c  ldloc.1
0x11901d  call     class System.Windows.Documents.TextPointer System.Windows.Documents.TextRangeEditTables::EnsureInsertionPosition(class System.Windows.Documents.TextPointer position)
0x119022  stloc.1
0x119023  ldloc.1
0x119024  callvirt instance class System.Windows.Documents.Paragraph System.Windows.Documents.TextPointer::get_Paragraph()
0x119029  stloc.s  4
0x11902b  ldloc.s  4
0x11902d  ldnull
0x11902e  cgt.un
0x119030  ldstr    aEnsureinsertio_2// "EnsureInsertionPosition must create a p"...
0x119035  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x11903a  ldloc.3
0x11903b  brfalse.s loc_11904C
0x11903d  ldloc.s  4
0x11903f  brfalse.s loc_11904C
0x119041  ldloc.3
0x119042  ldloc.s  4
0x119044  call     bool System.Windows.Documents.TextRangeEditLists::MergeParagraphs(class System.Windows.Documents.Block firstParagraphOrBlockUIContainer, class System.Windows.Documents.Block secondParagraphOrBlockUIContainer)
0x119049  pop
0x11904a  br.s     loc_119053
0x11904c  ldloc.0
0x11904d  ldloc.1
0x11904e  call     void System.Windows.Documents.TextRangeEdit::MergeEmptyParagraphsAndBlockUIContainers(class System.Windows.Documents.TextPointer startPosition, class System.Windows.Documents.TextPointer endPosition)
0x119053  ldloc.0
0x119054  call     bool System.Windows.Documents.TextRangeEdit::MergeFormattingInlines(class System.Windows.Documents.TextPointer position)
0x119059  pop
0x11905a  ldloc.1
0x11905b  call     bool System.Windows.Documents.TextRangeEdit::MergeFormattingInlines(class System.Windows.Documents.TextPointer position)
0x119060  pop
0x119061  ldloc.0
0x119062  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x119067  isinst   System.Windows.Documents.BlockUIContainer
0x11906c  brfalse.s loc_119093
0x11906e  ldloc.0
0x11906f  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x119074  castclass System.Windows.Documents.BlockUIContainer
0x119079  callvirt instance bool System.Windows.Documents.TextElement::get_IsEmpty()
0x11907e  brfalse.s loc_119093
0x119080  ldloc.0
0x119081  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x119086  castclass System.Windows.Documents.BlockUIContainer
0x11908b  ldnull
0x11908c  ldnull
0x11908d  callvirt instance void System.Windows.Documents.TextElement::Reposition(class System.Windows.Documents.TextPointer start, class System.Windows.Documents.TextPointer end)
0x119092  ret
0x119093  ldloc.0
0x119094  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x119099  isinst   System.Windows.Documents.Hyperlink
0x11909e  brfalse.s loc_1190CB
0x1190a0  ldloc.0
0x1190a1  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x1190a6  castclass System.Windows.Documents.Hyperlink
0x1190ab  callvirt instance bool System.Windows.Documents.TextElement::get_IsEmpty()
0x1190b0  brfalse.s loc_1190CB
0x1190b2  ldloc.0
0x1190b3  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Documents.TextPointer::get_Parent()
0x1190b8  castclass System.Windows.Documents.Hyperlink
0x1190bd  ldnull
0x1190be  ldnull
0x1190bf  callvirt instance void System.Windows.Documents.TextElement::Reposition(class System.Windows.Documents.TextPointer start, class System.Windows.Documents.TextPointer end)
0x1190c4  ldloc.0
0x1190c5  call     bool System.Windows.Documents.TextRangeEdit::MergeFormattingInlines(class System.Windows.Documents.TextPointer position)
0x1190ca  pop
0x1190cb  ret
```
