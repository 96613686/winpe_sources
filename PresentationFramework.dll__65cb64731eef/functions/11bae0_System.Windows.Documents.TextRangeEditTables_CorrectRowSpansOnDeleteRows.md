# System.Windows.Documents.TextRangeEditTables::CorrectRowSpansOnDeleteRows

- ea: `0x11bae0`
- end: `0x11bc3d`
- name: `System.Windows.Documents.TextRangeEditTables::CorrectRowSpansOnDeleteRows`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x11b900`

## callees

- `0x100160`
- `0x100420`
- `0x1004a0`
- `0x1008e0`
- `0x100940`
- `0x1011a0`
- `0x1011c0`
- `0x101220`
- `0x101c10`
- `0x10e890`
- `0x113720`
- `0x11bae0`
- `0x11c800`

## string_xrefs

- `0x11bafa`: `nextRow.Index is expected to be >= deletedRowsCount`
- `0x11bb57`: `spannedCell.RowSpan is expected to be > deletedRowsCount`

## pseudocode

```c

```

## disassembly

```asm
0x11bae0  ldarg.0
0x11bae1  ldnull
0x11bae2  cgt.un
0x11bae4  ldstr    aNullCheckNextr// "null check: nextRow"
0x11bae9  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x11baee  ldarg.0
0x11baef  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11baf4  ldarg.1
0x11baf5  clt
0x11baf7  ldc.i4.0
0x11baf8  ceq
0x11bafa  ldstr    aNextrowIndexIs// "nextRow.Index is expected to be >= dele"...
0x11baff  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x11bb04  ldarg.0
0x11bb05  callvirt instance class System.Windows.Documents.TableCellCollection System.Windows.Documents.TableRow::get_Cells()
0x11bb0a  stloc.0
0x11bb0b  ldarg.0
0x11bb0c  callvirt instance class System.Windows.Documents.TableCell[] System.Windows.Documents.TableRow::get_SpannedCells()
0x11bb11  stloc.1
0x11bb12  ldloc.1
0x11bb13  brfalse  loc_11BC3C
0x11bb18  ldc.i4.0
0x11bb19  stloc.2
0x11bb1a  ldc.i4.0
0x11bb1b  stloc.3
0x11bb1c  br       loc_11BC33
0x11bb21  ldloc.1
0x11bb22  ldloc.3
0x11bb23  ldelem.ref
0x11bb24  stloc.s  4
0x11bb26  ldloc.s  4
0x11bb28  callvirt instance class System.Windows.Documents.TableRow System.Windows.Documents.TableCell::get_Row()
0x11bb2d  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bb32  stloc.s  5
0x11bb34  ldloc.s  5
0x11bb36  ldarg.0
0x11bb37  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bb3c  bge      loc_11BC2F
0x11bb41  ldloc.s  5
0x11bb43  ldarg.0
0x11bb44  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bb49  ldarg.1
0x11bb4a  sub
0x11bb4b  bge.s    loc_11BB91
0x11bb4d  ldloc.s  4
0x11bb4f  callvirt instance int32 System.Windows.Documents.TableCell::get_RowSpan()
0x11bb54  ldarg.1
0x11bb55  cgt
0x11bb57  ldstr    aSpannedcellRow// "spannedCell.RowSpan is expected to be >"...
0x11bb5c  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x11bb61  ldloc.s  4
0x11bb63  callvirt instance class System.Windows.Documents.TextPointer System.Windows.Documents.TextElement::get_ContentStart()
0x11bb68  callvirt instance class System.Windows.Documents.TextContainer System.Windows.Documents.TextPointer::get_TextContainer()
0x11bb6d  ldloc.s  4
0x11bb6f  callvirt instance class System.Windows.Documents.TextPointer System.Windows.Documents.TextElement::get_ContentStart()
0x11bb74  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.TableCell::RowSpanProperty
0x11bb79  ldloc.s  4
0x11bb7b  callvirt instance int32 System.Windows.Documents.TableCell::get_RowSpan()
0x11bb80  ldarg.1
0x11bb81  sub
0x11bb82  box      [mscorlib]System.Int32
0x11bb87  callvirt instance void System.Windows.Documents.TextContainer::SetValue(class System.Windows.Documents.TextPointer position, class [WindowsBase]System.Windows.DependencyProperty property, object value)
0x11bb8c  br       loc_11BC2F
0x11bb91  ldloc.s  4
0x11bb93  callvirt instance int32 System.Windows.Documents.TableCell::get_ColumnIndex()
0x11bb98  stloc.s  6
0x11bb9a  br.s     loc_11BBA0
0x11bb9c  ldloc.2
0x11bb9d  ldc.i4.1
0x11bb9e  add
0x11bb9f  stloc.2
0x11bba0  ldloc.2
0x11bba1  ldloc.0
0x11bba2  callvirt instance int32 System.Windows.Documents.TableCellCollection::get_Count()
0x11bba7  bge.s    loc_11BBB9
0x11bba9  ldloc.0
0x11bbaa  ldloc.2
0x11bbab  callvirt instance class System.Windows.Documents.TableCell System.Windows.Documents.TableCellCollection::get_Item(int32 index)
0x11bbb0  callvirt instance int32 System.Windows.Documents.TableCell::get_ColumnIndex()
0x11bbb5  ldloc.s  6
0x11bbb7  blt.s    loc_11BB9C
0x11bbb9  ldarg.0
0x11bbba  ldloc.s  4
0x11bbbc  ldloc.2
0x11bbbd  ldc.i4.0
0x11bbbe  ldc.i4.1
0x11bbbf  call     class System.Windows.Documents.TableCell System.Windows.Documents.TextRangeEditTables::AddCellCopy(class System.Windows.Documents.TableRow newRow, class System.Windows.Documents.TableCell currentCell, int32 cellInsertionIndex, bool copyRowSpan, bool copyColumnSpan)
0x11bbc4  stloc.s  7
0x11bbc6  ldloc.s  4
0x11bbc8  callvirt instance int32 System.Windows.Documents.TableCell::get_RowSpan()
0x11bbcd  ldarg.0
0x11bbce  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bbd3  ldloc.s  4
0x11bbd5  callvirt instance class System.Windows.Documents.TableRow System.Windows.Documents.TableCell::get_Row()
0x11bbda  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bbdf  sub
0x11bbe0  sub
0x11bbe1  ldc.i4.0
0x11bbe2  cgt
0x11bbe4  ldstr    aExpectingSpann// "expecting: spannedCell.RowSpan - (nextR"...
0x11bbe9  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x11bbee  ldloc.s  7
0x11bbf0  callvirt instance class System.Windows.Documents.TextPointer System.Windows.Documents.TextElement::get_ContentStart()
0x11bbf5  callvirt instance class System.Windows.Documents.TextContainer System.Windows.Documents.TextPointer::get_TextContainer()
0x11bbfa  ldloc.s  7
0x11bbfc  callvirt instance class System.Windows.Documents.TextPointer System.Windows.Documents.TextElement::get_ContentStart()
0x11bc01  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Documents.TableCell::RowSpanProperty
0x11bc06  ldloc.s  4
0x11bc08  callvirt instance int32 System.Windows.Documents.TableCell::get_RowSpan()
0x11bc0d  ldarg.0
0x11bc0e  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bc13  ldloc.s  4
0x11bc15  callvirt instance class System.Windows.Documents.TableRow System.Windows.Documents.TableCell::get_Row()
0x11bc1a  callvirt instance int32 System.Windows.Documents.TableRow::get_Index()
0x11bc1f  sub
0x11bc20  sub
0x11bc21  box      [mscorlib]System.Int32
0x11bc26  callvirt instance void System.Windows.Documents.TextContainer::SetValue(class System.Windows.Documents.TextPointer position, class [WindowsBase]System.Windows.DependencyProperty property, object value)
0x11bc2b  ldloc.2
0x11bc2c  ldc.i4.1
0x11bc2d  add
0x11bc2e  stloc.2
0x11bc2f  ldloc.3
0x11bc30  ldc.i4.1
0x11bc31  add
0x11bc32  stloc.3
0x11bc33  ldloc.3
0x11bc34  ldloc.1
0x11bc35  ldlen
0x11bc36  conv.i4
0x11bc37  blt      loc_11BB21
0x11bc3c  ret
```
