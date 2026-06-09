# System.Windows.Markup.XamlTypeMapper::GetTypeFromBaseString

- ea: `0xaaaa0`
- end: `0xaabc0`
- name: `System.Windows.Markup.XamlTypeMapper::GetTypeFromBaseString`
- size: `288`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x95050`
- `0x9a610`
- `0xac980`
- `0xadbb0`

## callees

- `0xa8c30`
- `0xaaa90`
- `0xaaaa0`
- `0xab260`
- `0xad120`
- `0xad430`
- `0xad450`
- `0xb4030`

## string_xrefs

- `0xaab0e`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`
- `0xaab1b`: `SystemParameters`

## pseudocode

```c

```

## disassembly

```asm
0xaaaa0  ldsfld   string [mscorlib]System.String::Empty
0xaaaa5  stloc.0
0xaaaa6  ldnull
0xaaaa7  stloc.1
0xaaaa8  ldarg.1
0xaaaa9  ldc.i4.s 0x3A
0xaaaab  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xaaab0  stloc.2
0xaaab1  ldloc.2
0xaaab2  ldc.i4.m1
0xaaab3  bne.un.s loc_AAADB
0xaaab5  ldarg.2
0xaaab6  callvirt instance class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.ParserContext::get_XmlnsDictionary()
0xaaabb  ldsfld   string [mscorlib]System.String::Empty
0xaaac0  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0xaaac5  stloc.0
0xaaac6  ldloc.0
0xaaac7  brtrue.s loc_AAB0D
0xaaac9  ldarg.0
0xaaaca  ldstr    aParserundeclar// "ParserUndeclaredNS"
0xaaacf  ldsfld   string [mscorlib]System.String::Empty
0xaaad4  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter)
0xaaad9  br.s     loc_AAB0D
0xaaadb  ldarg.1
0xaaadc  ldc.i4.0
0xaaadd  ldloc.2
0xaaade  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xaaae3  stloc.3
0xaaae4  ldarg.2
0xaaae5  callvirt instance class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.ParserContext::get_XmlnsDictionary()
0xaaaea  ldloc.3
0xaaaeb  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0xaaaf0  stloc.0
0xaaaf1  ldloc.0
0xaaaf2  brtrue.s loc_AAB02
0xaaaf4  ldarg.0
0xaaaf5  ldstr    aParserundeclar// "ParserUndeclaredNS"
0xaaafa  ldloc.3
0xaaafb  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter)
0xaab00  br.s     loc_AAB0D
0xaab02  ldarg.1
0xaab03  ldloc.2
0xaab04  ldc.i4.1
0xaab05  add
0xaab06  callvirt instance string [mscorlib]System.String::Substring(int32)
0xaab0b  starg.s  1
0xaab0d  ldloc.0
0xaab0e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0xaab13  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xaab18  brtrue.s loc_AAB68
0xaab1a  ldarg.1
0xaab1b  ldstr    aSystemparamete_3// "SystemParameters"
0xaab20  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaab25  brtrue.s loc_AAB43
0xaab27  ldarg.1
0xaab28  ldstr    aSystemcolors// "SystemColors"
0xaab2d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaab32  brtrue.s loc_AAB50
0xaab34  ldarg.1
0xaab35  ldstr    aSystemfonts// "SystemFonts"
0xaab3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaab3f  brtrue.s loc_AAB5D
0xaab41  br.s     loc_AAB68
0xaab43  ldtoken  System.Windows.SystemParameters
0xaab48  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaab4d  stloc.1
0xaab4e  br.s     loc_AAB68
0xaab50  ldtoken  System.Windows.SystemColors
0xaab55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaab5a  stloc.1
0xaab5b  br.s     loc_AAB68
0xaab5d  ldtoken  System.Windows.SystemFonts
0xaab62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaab67  stloc.1
0xaab68  ldloc.1
0xaab69  ldnull
0xaab6a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaab6f  brfalse.s loc_AAB7A
0xaab71  ldarg.0
0xaab72  ldloc.0
0xaab73  ldarg.1
0xaab74  call     instance class [mscorlib]System.Type System.Windows.Markup.XamlTypeMapper::GetType(string xmlNamespace, string localName)
0xaab79  stloc.1
0xaab7a  ldloc.1
0xaab7b  ldnull
0xaab7c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaab81  ldarg.3
0xaab82  and
0xaab83  brfalse.s loc_AABBE
0xaab85  ldarg.0
0xaab86  ldloc.0
0xaab87  call     instance bool System.Windows.Markup.XamlTypeMapper::IsLocalAssembly(string namespaceUri)
0xaab8c  brtrue.s loc_AABBE
0xaab8e  ldarg.0
0xaab8f  ldarg.2
0xaab90  brtrue.s loc_AAB95
0xaab92  ldc.i4.0
0xaab93  br.s     loc_AAB9B
0xaab95  ldarg.2
0xaab96  callvirt instance int32 System.Windows.Markup.ParserContext::get_LineNumber()
0xaab9b  stfld    int32 System.Windows.Markup.XamlTypeMapper::_lineNumber
0xaaba0  ldarg.0
0xaaba1  ldarg.2
0xaaba2  brtrue.s loc_AABA7
0xaaba4  ldc.i4.0
0xaaba5  br.s     loc_AABAD
0xaaba7  ldarg.2
0xaaba8  callvirt instance int32 System.Windows.Markup.ParserContext::get_LinePosition()
0xaabad  stfld    int32 System.Windows.Markup.XamlTypeMapper::_linePosition
0xaabb2  ldarg.0
0xaabb3  ldstr    aParserresource// "ParserResourceKeyType"
0xaabb8  ldarg.1
0xaabb9  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id, string parameter)
0xaabbe  ldloc.1
0xaabbf  ret
```
