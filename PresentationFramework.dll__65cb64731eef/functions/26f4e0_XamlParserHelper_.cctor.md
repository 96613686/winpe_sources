# XamlParserHelper::.cctor

- ea: `0x26f4e0`
- end: `0x26fc06`
- name: `XamlParserHelper::.cctor`
- size: `1830`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x288d10`

## string_xrefs

- `0x26f8a5`: `NavigateUri`
- `0x26f543`: `Hyperlink`
- `0x26f8e1`: `xml:lang`
- `0x26f91d`: `UriSource`

## pseudocode

```c

```

## disassembly

```asm
0x26f4e0  ldc.i4.s 0x19
0x26f4e2  newarr   LookupTableEntry
0x26f4e7  dup
0x26f4e8  ldc.i4.0
0x26f4e9  ldstr    asc_28A0A2// ""
0x26f4ee  ldc.i4.0
0x26f4ef  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f4f4  stelem   LookupTableEntry
0x26f4f9  dup
0x26f4fa  ldc.i4.1
0x26f4fb  ldstr    asc_28A0A2// ""
0x26f500  ldc.i4.0
0x26f501  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f506  stelem   LookupTableEntry
0x26f50b  dup
0x26f50c  ldc.i4.2
0x26f50d  ldstr    aBold// "Bold"
0x26f512  ldc.i4.1
0x26f513  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f518  stelem   LookupTableEntry
0x26f51d  dup
0x26f51e  ldc.i4.3
0x26f51f  ldstr    aItalic// "Italic"
0x26f524  ldc.i4.2
0x26f525  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f52a  stelem   LookupTableEntry
0x26f52f  dup
0x26f530  ldc.i4.4
0x26f531  ldstr    aUnderline// "Underline"
0x26f536  ldc.i4.3
0x26f537  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f53c  stelem   LookupTableEntry
0x26f541  dup
0x26f542  ldc.i4.5
0x26f543  ldstr    aHyperlink// "Hyperlink"
0x26f548  ldc.i4.4
0x26f549  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f54e  stelem   LookupTableEntry
0x26f553  dup
0x26f554  ldc.i4.6
0x26f555  ldstr    aSpan// "Span"
0x26f55a  ldc.i4.5
0x26f55b  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f560  stelem   LookupTableEntry
0x26f565  dup
0x26f566  ldc.i4.7
0x26f567  ldstr    aRun// "Run"
0x26f56c  ldc.i4.5
0x26f56d  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f572  stelem   LookupTableEntry
0x26f577  dup
0x26f578  ldc.i4.8
0x26f579  ldstr    aLinebreak// "LineBreak"
0x26f57e  ldc.i4.6
0x26f57f  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f584  stelem   LookupTableEntry
0x26f589  dup
0x26f58a  ldc.i4.s 9
0x26f58c  ldstr    aParagraph// "Paragraph"
0x26f591  ldc.i4.7
0x26f592  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f597  stelem   LookupTableEntry
0x26f59c  dup
0x26f59d  ldc.i4.s 0xA
0x26f59f  ldstr    aInlineuicontai// "InlineUIContainer"
0x26f5a4  ldc.i4.5
0x26f5a5  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f5aa  stelem   LookupTableEntry
0x26f5af  dup
0x26f5b0  ldc.i4.s 0xB
0x26f5b2  ldstr    aBlockuicontain// "BlockUIContainer"
0x26f5b7  ldc.i4.s 9
0x26f5b9  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f5be  stelem   LookupTableEntry
0x26f5c3  dup
0x26f5c4  ldc.i4.s 0xC
0x26f5c6  ldstr    aImage_0// "Image"
0x26f5cb  ldc.i4.s 0xA
0x26f5cd  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f5d2  stelem   LookupTableEntry
0x26f5d7  dup
0x26f5d8  ldc.i4.s 0xD
0x26f5da  ldstr    aBitmapimage// "BitmapImage"
0x26f5df  ldc.i4.s 0xB
0x26f5e1  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f5e6  stelem   LookupTableEntry
0x26f5eb  dup
0x26f5ec  ldc.i4.s 0xE
0x26f5ee  ldstr    aList// "List"
0x26f5f3  ldc.i4.s 0xC
0x26f5f5  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f5fa  stelem   LookupTableEntry
0x26f5ff  dup
0x26f600  ldc.i4.s 0xF
0x26f602  ldstr    aListitem// "ListItem"
0x26f607  ldc.i4.s 0xD
0x26f609  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f60e  stelem   LookupTableEntry
0x26f613  dup
0x26f614  ldc.i4.s 0x10
0x26f616  ldstr    aTable// "Table"
0x26f61b  ldc.i4.s 0xE
0x26f61d  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f622  stelem   LookupTableEntry
0x26f627  dup
0x26f628  ldc.i4.s 0x11
0x26f62a  ldstr    aTablerowgroup// "TableRowGroup"
0x26f62f  ldc.i4.s 0xF
0x26f631  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f636  stelem   LookupTableEntry
0x26f63b  dup
0x26f63c  ldc.i4.s 0x12
0x26f63e  ldstr    aTablerow// "TableRow"
0x26f643  ldc.i4.s 0x10
0x26f645  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f64a  stelem   LookupTableEntry
0x26f64f  dup
0x26f650  ldc.i4.s 0x13
0x26f652  ldstr    aTablecell// "TableCell"
0x26f657  ldc.i4.s 0x11
0x26f659  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f65e  stelem   LookupTableEntry
0x26f663  dup
0x26f664  ldc.i4.s 0x14
0x26f666  ldstr    aTablecolumn// "TableColumn"
0x26f66b  ldc.i4.s 0x12
0x26f66d  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f672  stelem   LookupTableEntry
0x26f677  dup
0x26f678  ldc.i4.s 0x15
0x26f67a  ldstr    aSection// "Section"
0x26f67f  ldc.i4.s 0x13
0x26f681  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f686  stelem   LookupTableEntry
0x26f68b  dup
0x26f68c  ldc.i4.s 0x16
0x26f68e  ldstr    aFigure// "Figure"
0x26f693  ldc.i4.s 0x15
0x26f695  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f69a  stelem   LookupTableEntry
0x26f69f  dup
0x26f6a0  ldc.i4.s 0x17
0x26f6a2  ldstr    aFloater// "Floater"
0x26f6a7  ldc.i4.s 0x14
0x26f6a9  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f6ae  stelem   LookupTableEntry
0x26f6b3  dup
0x26f6b4  ldc.i4.s 0x18
0x26f6b6  ldstr    aTextdecoration_0// "TextDecoration"
0x26f6bb  ldc.i4.s 0x16
0x26f6bd  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f6c2  stelem   LookupTableEntry
0x26f6c7  stsfld   valuetype LookupTableEntry[] XamlParserHelper::TagTable
0x26f6cc  ldc.i4.s 0x24
0x26f6ce  newarr   LookupTableEntry
0x26f6d3  dup
0x26f6d4  ldc.i4.0
0x26f6d5  ldstr    asc_28A0A2// ""
0x26f6da  ldc.i4.0
0x26f6db  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f6e0  stelem   LookupTableEntry
0x26f6e5  dup
0x26f6e6  ldc.i4.1
0x26f6e7  ldstr    aFontweight// "FontWeight"
0x26f6ec  ldc.i4.1
0x26f6ed  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f6f2  stelem   LookupTableEntry
0x26f6f7  dup
0x26f6f8  ldc.i4.2
0x26f6f9  ldstr    aFontsize// "FontSize"
0x26f6fe  ldc.i4.2
0x26f6ff  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f704  stelem   LookupTableEntry
0x26f709  dup
0x26f70a  ldc.i4.3
0x26f70b  ldstr    aFontstyle// "FontStyle"
0x26f710  ldc.i4.3
0x26f711  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f716  stelem   LookupTableEntry
0x26f71b  dup
0x26f71c  ldc.i4.4
0x26f71d  ldstr    aFontfamily// "FontFamily"
0x26f722  ldc.i4.4
0x26f723  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f728  stelem   LookupTableEntry
0x26f72d  dup
0x26f72e  ldc.i4.5
0x26f72f  ldstr    aBackground// "Background"
0x26f734  ldc.i4.6
0x26f735  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f73a  stelem   LookupTableEntry
0x26f73f  dup
0x26f740  ldc.i4.6
0x26f741  ldstr    aForeground// "Foreground"
0x26f746  ldc.i4.7
0x26f747  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f74c  stelem   LookupTableEntry
0x26f751  dup
0x26f752  ldc.i4.7
0x26f753  ldstr    aFlowdirection// "FlowDirection"
0x26f758  ldc.i4.8
0x26f759  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f75e  stelem   LookupTableEntry
0x26f763  dup
0x26f764  ldc.i4.8
0x26f765  ldstr    aTextdecoration// "TextDecorations"
0x26f76a  ldc.i4.s 9
0x26f76c  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f771  stelem   LookupTableEntry
0x26f776  dup
0x26f777  ldc.i4.s 9
0x26f779  ldstr    aTextalignment// "TextAlignment"
0x26f77e  ldc.i4.s 0xA
0x26f780  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f785  stelem   LookupTableEntry
0x26f78a  dup
0x26f78b  ldc.i4.s 0xA
0x26f78d  ldstr    aMarkerstyle// "MarkerStyle"
0x26f792  ldc.i4.s 0xB
0x26f794  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f799  stelem   LookupTableEntry
0x26f79e  dup
0x26f79f  ldc.i4.s 0xB
0x26f7a1  ldstr    aTextindent// "TextIndent"
0x26f7a6  ldc.i4.s 0xC
0x26f7a8  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f7ad  stelem   LookupTableEntry
0x26f7b2  dup
0x26f7b3  ldc.i4.s 0xC
0x26f7b5  ldstr    aColumnspan// "ColumnSpan"
0x26f7ba  ldc.i4.s 0xD
0x26f7bc  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f7c1  stelem   LookupTableEntry
0x26f7c6  dup
0x26f7c7  ldc.i4.s 0xD
0x26f7c9  ldstr    aRowspan// "RowSpan"
0x26f7ce  ldc.i4.s 0xE
0x26f7d0  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f7d5  stelem   LookupTableEntry
0x26f7da  dup
0x26f7db  ldc.i4.s 0xE
0x26f7dd  ldstr    aStartindex_0// "StartIndex"
0x26f7e2  ldc.i4.s 0xF
0x26f7e4  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f7e9  stelem   LookupTableEntry
0x26f7ee  dup
0x26f7ef  ldc.i4.s 0xF
0x26f7f1  ldstr    aMarkeroffset// "MarkerOffset"
0x26f7f6  ldc.i4.s 0x10
0x26f7f8  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f7fd  stelem   LookupTableEntry
0x26f802  dup
0x26f803  ldc.i4.s 0x10
0x26f805  ldstr    aBorderthicknes// "BorderThickness"
0x26f80a  ldc.i4.s 0x11
0x26f80c  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f811  stelem   LookupTableEntry
0x26f816  dup
0x26f817  ldc.i4.s 0x11
0x26f819  ldstr    aBorderbrush// "BorderBrush"
0x26f81e  ldc.i4.s 0x12
0x26f820  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f825  stelem   LookupTableEntry
0x26f82a  dup
0x26f82b  ldc.i4.s 0x12
0x26f82d  ldstr    aPadding// "Padding"
0x26f832  ldc.i4.s 0x13
0x26f834  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f839  stelem   LookupTableEntry
0x26f83e  dup
0x26f83f  ldc.i4.s 0x13
0x26f841  ldstr    aMargin// "Margin"
0x26f846  ldc.i4.s 0x14
0x26f848  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f84d  stelem   LookupTableEntry
0x26f852  dup
0x26f853  ldc.i4.s 0x14
0x26f855  ldstr    aKeeptogether// "KeepTogether"
0x26f85a  ldc.i4.s 0x15
0x26f85c  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f861  stelem   LookupTableEntry
0x26f866  dup
0x26f867  ldc.i4.s 0x15
0x26f869  ldstr    aKeepwithnext// "KeepWithNext"
0x26f86e  ldc.i4.s 0x16
0x26f870  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f875  stelem   LookupTableEntry
0x26f87a  dup
0x26f87b  ldc.i4.s 0x16
0x26f87d  ldstr    aBaselinealignm// "BaselineAlignment"
0x26f882  ldc.i4.s 0x17
0x26f884  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f889  stelem   LookupTableEntry
0x26f88e  dup
0x26f88f  ldc.i4.s 0x17
0x26f891  ldstr    aBaselineoffset// "BaselineOffset"
0x26f896  ldc.i4.s 0x18
0x26f898  newobj   instance void LookupTableEntry::.ctor(string name, int32 value)
0x26f89d  stelem   LookupTableEntry
0x26f8a2  dup
  ... truncated ...
```
