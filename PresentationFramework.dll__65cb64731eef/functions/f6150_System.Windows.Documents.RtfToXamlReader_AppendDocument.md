# System.Windows.Documents.RtfToXamlReader::AppendDocument

- ea: `0xf6150`
- end: `0xf6283`
- name: `System.Windows.Documents.RtfToXamlReader::AppendDocument`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf5f30`

## callees

- `0xf4070`
- `0xf4160`
- `0xf4420`
- `0xf48b0`
- `0xf4d30`
- `0xf4ee0`
- `0xf5690`
- `0xf5db0`
- `0xf5dc0`
- `0xf60c0`
- `0xf6100`
- `0xf6150`
- `0xf8750`

## string_xrefs

- `0xf620c`: `<Section xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xml:space="preserve" >\n`
- `0xf621f`: `<Span xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xml:space="preserve">`

## pseudocode

```c

```

## disassembly

```asm
0xf6150  ldarg.0
0xf6151  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.RtfToXamlReader::_converterState
0xf6156  callvirt instance class System.Windows.Documents.DocumentNodeArray System.Windows.Documents.ConverterState::get_DocumentNodeArray()
0xf615b  stloc.0
0xf615c  br.s     loc_F618C
0xf615e  ldloc.0
0xf615f  ldloc.0
0xf6160  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf6165  ldc.i4.1
0xf6166  sub
0xf6167  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf616c  stloc.2
0xf616d  ldloc.2
0xf616e  callvirt instance bool System.Windows.Documents.DocumentNode::get_IsInline()
0xf6173  brfalse.s loc_F6195
0xf6175  ldloc.2
0xf6176  callvirt instance bool System.Windows.Documents.DocumentNode::get_IsWhiteSpace()
0xf617b  brfalse.s loc_F6195
0xf617d  ldloc.0
0xf617e  ldloc.0
0xf617f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf6184  ldc.i4.1
0xf6185  sub
0xf6186  ldc.i4.1
0xf6187  callvirt instance void System.Windows.Documents.DocumentNodeArray::Excise(int32 nAt, int32 nExcise)
0xf618c  ldloc.0
0xf618d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf6192  ldc.i4.0
0xf6193  bgt.s    loc_F615E
0xf6195  ldarg.0
0xf6196  call     instance bool System.Windows.Documents.RtfToXamlReader::get_ForceParagraph()
0xf619b  brtrue.s loc_F61A5
0xf619d  ldarg.0
0xf619e  call     instance bool System.Windows.Documents.RtfToXamlReader::TreeContainsBlock()
0xf61a3  brfalse.s loc_F61DF
0xf61a5  ldloc.0
0xf61a6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf61ab  ldc.i4.0
0xf61ac  ble.s    loc_F61DF
0xf61ae  ldloc.0
0xf61af  ldloc.0
0xf61b0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf61b5  ldc.i4.1
0xf61b6  sub
0xf61b7  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf61bc  stloc.3
0xf61bd  ldloc.3
0xf61be  callvirt instance bool System.Windows.Documents.DocumentNode::get_IsInline()
0xf61c3  brfalse.s loc_F61DF
0xf61c5  ldarg.0
0xf61c6  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.RtfToXamlReader::_converterState
0xf61cb  callvirt instance class System.Windows.Documents.FormatState System.Windows.Documents.ConverterState::get_TopFormatState()
0xf61d0  stloc.s  4
0xf61d2  ldloc.s  4
0xf61d4  brfalse.s loc_F61DF
0xf61d6  ldarg.0
0xf61d7  ldnull
0xf61d8  ldloc.s  4
0xf61da  call     instance void System.Windows.Documents.RtfToXamlReader::HandlePara(class System.Windows.Documents.RtfToken token, class System.Windows.Documents.FormatState formatState)
0xf61df  ldloc.0
0xf61e0  callvirt instance void System.Windows.Documents.DocumentNodeArray::CloseAll()
0xf61e5  ldloc.0
0xf61e6  ldarg.0
0xf61e7  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.RtfToXamlReader::_converterState
0xf61ec  callvirt instance void System.Windows.Documents.DocumentNodeArray::CoalesceAll(class System.Windows.Documents.ConverterState converterState)
0xf61f1  ldarg.0
0xf61f2  call     instance bool System.Windows.Documents.RtfToXamlReader::get_ForceParagraph()
0xf61f7  brtrue.s loc_F6201
0xf61f9  ldarg.0
0xf61fa  call     instance bool System.Windows.Documents.RtfToXamlReader::TreeContainsBlock()
0xf61ff  br.s     loc_F6202
0xf6201  ldc.i4.1
0xf6202  stloc.1
0xf6203  ldloc.1
0xf6204  brfalse.s loc_F6219
0xf6206  ldarg.0
0xf6207  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.RtfToXamlReader::_outerXamlBuilder
0xf620c  ldstr    aSectionXmlnsHt// "<Section xmlns=\"http://schemas.microso"...
0xf6211  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6216  pop
0xf6217  br.s     loc_F622A
0xf6219  ldarg.0
0xf621a  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.RtfToXamlReader::_outerXamlBuilder
0xf621f  ldstr    aSpanXmlnsHttpS// "<Span xmlns=\"http://schemas.microsoft."...
0xf6224  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6229  pop
0xf622a  ldc.i4.0
0xf622b  stloc.s  5
0xf622d  br.s     loc_F6252
0xf622f  ldloc.0
0xf6230  ldloc.s  5
0xf6232  callvirt instance class System.Windows.Documents.DocumentNode System.Windows.Documents.DocumentNodeArray::EntryAt(int32 nAt)
0xf6237  stloc.s  6
0xf6239  ldarg.0
0xf623a  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.RtfToXamlReader::_outerXamlBuilder
0xf623f  ldloc.s  6
0xf6241  callvirt instance string System.Windows.Documents.DocumentNode::get_Xaml()
0xf6246  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf624b  pop
0xf624c  ldloc.s  5
0xf624e  ldc.i4.1
0xf624f  add
0xf6250  stloc.s  5
0xf6252  ldloc.s  5
0xf6254  ldloc.0
0xf6255  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xf625a  blt.s    loc_F622F
0xf625c  ldloc.1
0xf625d  brfalse.s loc_F6271
0xf625f  ldarg.0
0xf6260  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.RtfToXamlReader::_outerXamlBuilder
0xf6265  ldstr    aSection_0// "</Section>"
0xf626a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf626f  pop
0xf6270  ret
0xf6271  ldarg.0
0xf6272  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.RtfToXamlReader::_outerXamlBuilder
0xf6277  ldstr    aSpan_1// "</Span>"
0xf627c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf6281  pop
0xf6282  ret
```
