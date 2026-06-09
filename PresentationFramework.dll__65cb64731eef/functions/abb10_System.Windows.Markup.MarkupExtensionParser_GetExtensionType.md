# System.Windows.Markup.MarkupExtensionParser::GetExtensionType

- ea: `0xabb10`
- end: `0xabbd7`
- name: `System.Windows.Markup.MarkupExtensionParser::GetExtensionType`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0xab9c0`
- `0xaba10`

## callees

- `0xa4f70`
- `0xa8b00`
- `0xab5b0`
- `0xab5c0`
- `0xab5d0`
- `0xabb10`
- `0xacc50`

## string_xrefs

- `0xabb82`: `ParserNotMarkupExtension`
- `0xabbc3`: `ParserNotMarkupExtension`

## pseudocode

```c

```

## disassembly

```asm
0xabb10  ldarg.s  6
0xabb12  ldnull
0xabb13  stind.ref
0xabb14  ldarg.s  7
0xabb16  ldnull
0xabb17  stind.ref
0xabb18  ldarg.s  8
0xabb1a  ldnull
0xabb1b  stind.ref
0xabb1c  ldarg.s  9
0xabb1e  ldnull
0xabb1f  stind.ref
0xabb20  ldarg.1
0xabb21  stloc.0
0xabb22  ldsfld   string [mscorlib]System.String::Empty
0xabb27  stloc.1
0xabb28  ldarg.1
0xabb29  ldc.i4.s 0x3A
0xabb2b  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xabb30  stloc.2
0xabb31  ldloc.2
0xabb32  ldc.i4.0
0xabb33  blt.s    loc_ABB49
0xabb35  ldarg.1
0xabb36  ldc.i4.0
0xabb37  ldloc.2
0xabb38  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xabb3d  stloc.1
0xabb3e  ldarg.1
0xabb3f  ldloc.2
0xabb40  ldc.i4.1
0xabb41  add
0xabb42  callvirt instance string [mscorlib]System.String::Substring(int32)
0xabb47  starg.s  1
0xabb49  ldarg.s  5
0xabb4b  ldarg.0
0xabb4c  ldfld    class System.Windows.Markup.IParserHelper System.Windows.Markup.MarkupExtensionParser::_parserHelper
0xabb51  ldloc.1
0xabb52  callvirt instance string System.Windows.Markup.IParserHelper::LookupNamespace(string prefix)
0xabb57  stind.ref
0xabb58  ldarg.0
0xabb59  ldfld    class System.Windows.Markup.IParserHelper System.Windows.Markup.MarkupExtensionParser::_parserHelper
0xabb5e  ldc.i4.1
0xabb5f  ldarg.1
0xabb60  ldarg.s  5
0xabb62  ldind.ref
0xabb63  ldarg.s  6
0xabb65  ldarg.s  7
0xabb67  ldarg.s  8
0xabb69  ldarg.s  9
0xabb6b  callvirt instance bool System.Windows.Markup.IParserHelper::GetElementType(bool extensionFirst, string localName, string namespaceURI, string& assemblyName, string& typeFullName, class [mscorlib]System.Type& baseType, class [mscorlib]System.Type& serializerType)
0xabb70  stloc.3
0xabb71  ldloc.3
0xabb72  brtrue.s loc_ABBA9
0xabb74  ldarg.0
0xabb75  ldfld    class System.Windows.Markup.IParserHelper System.Windows.Markup.MarkupExtensionParser::_parserHelper
0xabb7a  callvirt instance bool System.Windows.Markup.IParserHelper::CanResolveLocalAssemblies()
0xabb7f  brfalse.s loc_ABB96
0xabb81  ldarg.0
0xabb82  ldstr    aParsernotmarku// "ParserNotMarkupExtension"
0xabb87  ldarg.2
0xabb88  ldarg.1
0xabb89  ldarg.s  5
0xabb8b  ldind.ref
0xabb8c  ldarg.3
0xabb8d  ldarg.s  4
0xabb8f  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, string parameter2, string parameter3, int32 lineNumber, int32 linePosition)
0xabb94  br.s     loc_ABBD5
0xabb96  ldarg.s  7
0xabb98  ldloc.0
0xabb99  stind.ref
0xabb9a  ldarg.s  8
0xabb9c  ldtoken  UnknownMarkupExtension
0xabba1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xabba6  stind.ref
0xabba7  br.s     loc_ABBD5
0xabba9  call     class System.Windows.Markup.TypeIndexer System.Windows.Markup.KnownTypes::get_Types()
0xabbae  ldc.i4   0x17D
0xabbb3  callvirt instance class [mscorlib]System.Type System.Windows.Markup.TypeIndexer::get_Item(int32 index)
0xabbb8  ldarg.s  8
0xabbba  ldind.ref
0xabbbb  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0xabbc0  brtrue.s loc_ABBD5
0xabbc2  ldarg.0
0xabbc3  ldstr    aParsernotmarku// "ParserNotMarkupExtension"
0xabbc8  ldarg.2
0xabbc9  ldarg.1
0xabbca  ldarg.s  5
0xabbcc  ldind.ref
0xabbcd  ldarg.3
0xabbce  ldarg.s  4
0xabbd0  call     instance void System.Windows.Markup.MarkupExtensionParser::ThrowException(string id, string parameter1, string parameter2, string parameter3, int32 lineNumber, int32 linePosition)
0xabbd5  ldloc.3
0xabbd6  ret
```
