# System.Windows.Documents.RtfToXamlReader::ProcessField

- ea: `0xf6290`
- end: `0xf6785`
- name: `System.Windows.Documents.RtfToXamlReader::ProcessField`
- size: `1269`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0xf71f0`

## callees

- `0xefea0`
- `0xf33d0`
- `0xf4070`
- `0xf40b0`
- `0xf4130`
- `0xf41c0`
- `0xf42f0`
- `0xf4300`
- `0xf4360`
- `0xf4380`
- `0xf43d0`
- `0xf4420`
- `0xf4430`
- `0xf48b0`
- `0xf5630`
- `0xf5690`
- `0xf5db0`
- `0xf6290`
- `0xf67f0`
- `0xf6840`
- `0xf6a00`
- `0xf88b0`

## string_xrefs

- `0xf63ee`: `HYPERLINK`
- `0xf64ea`: `UriSource=`
- `0xf6523`: `UriSource="`
- `0xf661a`: `</Hyperlink>`
- `0xf66c4`: `</Hyperlink>`

## pseudocode

```c

```

## disassembly

```asm
0xf6290  ldarg.0
0xf6291  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.RtfToXamlReader::_converterState
0xf6296  callvirt instance class System.Windows.Documents.DocumentNodeArray System.Windows.Documents.ConverterState::get_DocumentNodeArray()
0xf629b  stloc.0
0xf629c  ldnull
0xf629d  stloc.1
0xf629e  ldnull
0xf629f  stloc.2
0xf62a0  ldnull
0xf62a1  stloc.3
0xf62a2  ldnull
0xf62a3  stloc.s  4
0xf62a5  ldnull
0xf62a6  stloc.s  5
0xf62a8  ldnull
0xf62a9  stloc.s  6
0xf62ab  ldloc.0
0xf62ac  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf62b1  ldc.i4.1
0xf62b2  sub
0xf62b3  stloc.s  0xD
0xf62b5  br       loc_F634B
0xf62ba  ldloc.0
0xf62bb  ldloc.s  0xD
0xf62bd  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf62c2  stloc.s  0xE
0xf62c4  ldloc.s  0xE
0xf62c6  callvirt instance valuetype System.Windows.Documents.DocumentNodeType System.Windows.Documents.DocumentNode::get_Type()
0xf62cb  ldc.i4.s 0x12
0xf62cd  bne.un.s loc_F6305
0xf62cf  ldloc.s  0xE
0xf62d1  callvirt instance class System.Windows.Documents.FormatState System.Windows.Documents.DocumentNode::get_FormatState()
0xf62d6  callvirt instance valuetype System.Windows.Documents.RtfDestination System.Windows.Documents.FormatState::get_RtfDestination()
0xf62db  stloc.s  0xF
0xf62dd  ldloc.s  0xF
0xf62df  ldc.i4.s 0xC
0xf62e1  sub
0xf62e2  switch   loc_F6300, loc_F62F5, loc_F62FA
0xf62f3  br.s     loc_F6345
0xf62f5  ldloc.s  0xE
0xf62f7  stloc.3
0xf62f8  br.s     loc_F6345
0xf62fa  ldloc.s  0xE
0xf62fc  stloc.s  5
0xf62fe  br.s     loc_F6345
0xf6300  ldloc.s  0xE
0xf6302  stloc.1
0xf6303  br.s     loc_F6345
0xf6305  ldloc.s  0xE
0xf6307  callvirt instance valuetype System.Windows.Documents.DocumentNodeType System.Windows.Documents.DocumentNode::get_Type()
0xf630c  ldc.i4.s 0x13
0xf630e  bne.un.s loc_F6345
0xf6310  ldloc.s  0xE
0xf6312  callvirt instance class System.Windows.Documents.FormatState System.Windows.Documents.DocumentNode::get_FormatState()
0xf6317  callvirt instance valuetype System.Windows.Documents.RtfDestination System.Windows.Documents.FormatState::get_RtfDestination()
0xf631c  stloc.s  0x10
0xf631e  ldloc.s  0x10
0xf6320  ldc.i4.s 0xC
0xf6322  sub
0xf6323  switch   loc_F6342, loc_F6336, loc_F633C
0xf6334  br.s     loc_F6345
0xf6336  ldloc.s  0xE
0xf6338  stloc.s  4
0xf633a  br.s     loc_F6345
0xf633c  ldloc.s  0xE
0xf633e  stloc.s  6
0xf6340  br.s     loc_F6345
0xf6342  ldloc.s  0xE
0xf6344  stloc.2
0xf6345  ldloc.s  0xD
0xf6347  ldc.i4.1
0xf6348  sub
0xf6349  stloc.s  0xD
0xf634b  ldloc.s  0xD
0xf634d  ldc.i4.0
0xf634e  blt.s    loc_F6356
0xf6350  ldloc.1
0xf6351  brfalse  loc_F62BA
0xf6356  ldloc.1
0xf6357  brfalse.s loc_F635C
0xf6359  ldloc.2
0xf635a  brtrue.s loc_F635D
0xf635c  ret
0xf635d  ldnull
0xf635e  stloc.s  7
0xf6360  ldnull
0xf6361  stloc.s  8
0xf6363  ldloc.3
0xf6364  brfalse  loc_F643B
0xf6369  ldloc.s  4
0xf636b  brfalse  loc_F643B
0xf6370  ldloc.s  4
0xf6372  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf6377  ldloc.3
0xf6378  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf637d  ldc.i4.1
0xf637e  add
0xf637f  ble      loc_F643B
0xf6384  ldsfld   string [mscorlib]System.String::Empty
0xf6389  stloc.s  0x11
0xf638b  ldloc.3
0xf638c  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf6391  ldc.i4.1
0xf6392  add
0xf6393  stloc.s  0x12
0xf6395  br.s     loc_F63C1
0xf6397  ldloc.0
0xf6398  ldloc.s  0x12
0xf639a  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf639f  stloc.s  0x13
0xf63a1  ldloc.s  0x13
0xf63a3  callvirt instance valuetype System.Windows.Documents.DocumentNodeType System.Windows.Documents.DocumentNode::get_Type()
0xf63a8  ldc.i4.1
0xf63a9  bne.un.s loc_F63BB
0xf63ab  ldloc.s  0x11
0xf63ad  ldloc.s  0x13
0xf63af  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf63b4  call     string [mscorlib]System.String::Concat(string, string)
0xf63b9  stloc.s  0x11
0xf63bb  ldloc.s  0x12
0xf63bd  ldc.i4.1
0xf63be  add
0xf63bf  stloc.s  0x12
0xf63c1  ldloc.s  0x12
0xf63c3  ldloc.s  4
0xf63c5  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf63ca  blt.s    loc_F6397
0xf63cc  ldloc.s  0x11
0xf63ce  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf63d3  ldc.i4.0
0xf63d4  ble.s    loc_F63EC
0xf63d6  ldloc.s  0x11
0xf63d8  ldc.i4.0
0xf63d9  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xf63de  ldc.i4.s 0x20
0xf63e0  bne.un.s loc_F63EC
0xf63e2  ldloc.s  0x11
0xf63e4  ldc.i4.1
0xf63e5  callvirt instance string [mscorlib]System.String::Substring(int32)
0xf63ea  stloc.s  0x11
0xf63ec  ldloc.s  0x11
0xf63ee  ldstr    aHyperlink_0// "HYPERLINK"
0xf63f3  ldc.i4.4
0xf63f4  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xf63f9  brtrue.s loc_F6407
0xf63fb  ldarg.0
0xf63fc  ldloc.s  0x11
0xf63fe  call     instance class System.Windows.Documents.DocumentNode System.Windows.Documents.RtfToXamlReader::ProcessHyperlinkField(string instr)
0xf6403  stloc.s  7
0xf6405  br.s     loc_F643B
0xf6407  ldloc.s  0x11
0xf6409  ldstr    aSymbol// "SYMBOL"
0xf640e  ldc.i4.4
0xf640f  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xf6414  brtrue.s loc_F6422
0xf6416  ldarg.0
0xf6417  ldloc.s  0x11
0xf6419  call     instance class System.Windows.Documents.DocumentNode System.Windows.Documents.RtfToXamlReader::ProcessSymbolField(string instr)
0xf641e  stloc.s  7
0xf6420  br.s     loc_F643B
0xf6422  ldloc.s  0x11
0xf6424  ldstr    aIncludepicture// "INCLUDEPICTURE"
0xf6429  ldc.i4.4
0xf642a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xf642f  brtrue.s loc_F643B
0xf6431  ldarg.0
0xf6432  ldloc.s  0x11
0xf6434  call     instance string System.Windows.Documents.RtfToXamlReader::GetIncludePictureUri(string instructionName)
0xf6439  stloc.s  8
0xf643b  ldloc.3
0xf643c  brfalse.s loc_F6462
0xf643e  ldloc.s  4
0xf6440  brfalse.s loc_F6462
0xf6442  ldloc.s  4
0xf6444  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf6449  ldloc.3
0xf644a  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf644f  sub
0xf6450  ldc.i4.1
0xf6451  add
0xf6452  stloc.s  0x14
0xf6454  ldloc.0
0xf6455  ldloc.3
0xf6456  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf645b  ldloc.s  0x14
0xf645d  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf6462  ldloc.s  5
0xf6464  brfalse.s loc_F6474
0xf6466  ldloc.0
0xf6467  ldloc.s  5
0xf6469  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf646e  ldc.i4.1
0xf646f  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf6474  ldloc.s  6
0xf6476  brfalse.s loc_F6486
0xf6478  ldloc.0
0xf6479  ldloc.s  6
0xf647b  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf6480  ldc.i4.1
0xf6481  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf6486  ldloc.1
0xf6487  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf648c  stloc.s  9
0xf648e  ldloc.2
0xf648f  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf6494  ldloc.1
0xf6495  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf649a  sub
0xf649b  ldc.i4.1
0xf649c  sub
0xf649d  stloc.s  0xA
0xf649f  ldloc.1
0xf64a0  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNode::get_ClosedParent()
0xf64a5  stloc.s  0xB
0xf64a7  ldloc.0
0xf64a8  ldloc.1
0xf64a9  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf64ae  ldc.i4.1
0xf64af  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf64b4  ldloc.0
0xf64b5  ldloc.2
0xf64b6  callvirt instance int32 System.Windows.Documents.DocumentNode::get_Index()
0xf64bb  ldc.i4.1
0xf64bc  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf64c1  ldloc.s  8
0xf64c3  brfalse  loc_F6558
0xf64c8  ldloc.s  0xA
0xf64ca  brfalse  loc_F6558
0xf64cf  ldloc.0
0xf64d0  ldloc.s  9
0xf64d2  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf64d7  stloc.s  0x15
0xf64d9  ldloc.s  0x15
0xf64db  callvirt instance valuetype System.Windows.Documents.DocumentNodeType System.Windows.Documents.DocumentNode::get_Type()
0xf64e0  ldc.i4.8
0xf64e1  bne.un.s loc_F6558
0xf64e3  ldloc.s  0x15
0xf64e5  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf64ea  ldstr    aUrisource// "UriSource="
0xf64ef  ldc.i4.4
0xf64f0  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xf64f5  stloc.s  0x16
0xf64f7  ldloc.s  0x15
0xf64f9  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf64fe  ldstr    asc_29CCCE// "\""
0xf6503  ldloc.s  0x16
0xf6505  ldc.i4.s 0xB
0xf6507  add
0xf6508  ldc.i4.4
0xf6509  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0xf650e  stloc.s  0x17
0xf6510  ldloc.s  0x15
0xf6512  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf6517  ldc.i4.0
0xf6518  ldloc.s  0x16
0xf651a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xf651f  stloc.s  0x18
0xf6521  ldloc.s  0x18
0xf6523  ldstr    aUrisource_0// "UriSource=\""
0xf6528  ldloc.s  8
0xf652a  ldstr    asc_29CCCE// "\""
0xf652f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xf6534  stloc.s  0x18
0xf6536  ldloc.s  0x18
0xf6538  ldloc.s  0x15
0xf653a  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf653f  ldloc.s  0x17
0xf6541  ldc.i4.1
0xf6542  add
0xf6543  callvirt instance string [mscorlib]System.String::Substring(int32)
0xf6548  call     string [mscorlib]System.String::Concat(string, string)
0xf654d  stloc.s  0x18
0xf654f  ldloc.s  0x15
0xf6551  ldloc.s  0x18
0xf6553  callvirt instance void System.Windows.Documents.DocumentNode::set_Xaml(string value)
0xf6558  ldloc.s  7
0xf655a  brfalse  loc_F66DD
0xf655f  ldc.i4.1
0xf6560  stloc.s  0x19
0xf6562  ldloc.s  7
0xf6564  callvirt instance bool System.Windows.Documents.DocumentNode::get_IsInline()
0xf6569  brfalse.s loc_F6596
0xf656b  ldloc.s  9
0xf656d  stloc.s  0x1A
0xf656f  br.s     loc_F6589
0xf6571  ldloc.0
0xf6572  ldloc.s  0x1A
0xf6574  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf6579  callvirt instance bool System.Windows.Documents.DocumentNode::get_IsBlock()
0xf657e  brfalse.s loc_F6583
0xf6580  ldc.i4.0
0xf6581  stloc.s  0x19
0xf6583  ldloc.s  0x1A
0xf6585  ldc.i4.1
0xf6586  add
0xf6587  stloc.s  0x1A
0xf6589  ldloc.s  0x19
0xf658b  brfalse.s loc_F6596
0xf658d  ldloc.s  0x1A
0xf658f  ldloc.s  9
  ... truncated ...
```
