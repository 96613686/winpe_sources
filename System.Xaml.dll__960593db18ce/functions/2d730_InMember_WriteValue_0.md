# InMember::WriteValue_0

- ea: `0x2d730`
- end: `0x2d8cc`
- name: `InMember::WriteValue_0`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x89f0`
- `0xa3f0`
- `0xd070`
- `0xd1a0`
- `0xef20`
- `0xefa0`
- `0xf990`
- `0xf9c0`
- `0xf9d0`
- `0xf9f0`
- `0xfa30`
- `0xfa90`
- `0x11f50`
- `0x2cb30`
- `0x2cb70`
- `0x2d730`
- `0x2d8d0`
- `0x2dab0`
- `0x2db70`

## string_xrefs

- `0x2d752`: `WriteValue`
- `0x2d745`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2d730  ldarg.1
0x2d731  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d736  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d73b  stloc.0
0x2d73c  ldloc.0
0x2d73d  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d742  ldc.i4.4
0x2d743  beq.s    loc_2D763
0x2d745  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2d74a  ldc.i4.1
0x2d74b  newarr   [mscorlib]System.Object
0x2d750  dup
0x2d751  ldc.i4.0
0x2d752  ldstr    aWritevalue// "WriteValue"
0x2d757  stelem.ref
0x2d758  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d75d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d762  throw
0x2d763  ldloc.0
0x2d764  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2d769  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2d76e  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x2d773  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d778  brfalse.s loc_2D796
0x2d77a  ldarg.1
0x2d77b  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d780  ldarg.2
0x2d781  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x2d786  ldarg.1
0x2d787  call     class WriterState InMemberAfterValue::get_State()
0x2d78c  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d791  br       loc_2D8B7
0x2d796  ldarg.2
0x2d797  call     bool System.Xaml.XamlXmlWriter::HasSignificantWhitespace(string s)
0x2d79c  brfalse  loc_2D8A0
0x2d7a1  ldarg.1
0x2d7a2  call     class System.Xaml.XamlType System.Xaml.XamlXmlWriter::GetContainingXamlType(class System.Xaml.XamlXmlWriter writer)
0x2d7a7  stloc.1
0x2d7a8  ldloc.1
0x2d7a9  ldnull
0x2d7aa  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d7af  brfalse.s loc_2D7DD
0x2d7b1  ldloc.1
0x2d7b2  callvirt instance bool System.Xaml.XamlType::get_IsWhitespaceSignificantCollection()
0x2d7b7  brtrue.s loc_2D7DD
0x2d7b9  ldarg.0
0x2d7ba  ldarg.1
0x2d7bb  ldarg.2
0x2d7bc  call     instance void InMember::WriteXmlSpaceOrThrow(class System.Xaml.XamlXmlWriter writer, string value)
0x2d7c1  ldarg.1
0x2d7c2  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d7c7  ldarg.2
0x2d7c8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x2d7cd  ldarg.1
0x2d7ce  call     class WriterState InMemberAfterValue::get_State()
0x2d7d3  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d7d8  br       loc_2D8B7
0x2d7dd  ldarg.2
0x2d7de  call     bool System.Xaml.XamlXmlWriter::ContainsConsecutiveInnerSpaces(string s)
0x2d7e3  brtrue.s loc_2D7ED
0x2d7e5  ldarg.2
0x2d7e6  call     bool System.Xaml.XamlXmlWriter::ContainsWhitespaceThatIsNotSpace(string s)
0x2d7eb  brfalse.s loc_2D83C
0x2d7ed  ldarg.1
0x2d7ee  ldfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d7f3  brfalse.s loc_2D819
0x2d7f5  ldarg.0
0x2d7f6  ldarg.1
0x2d7f7  ldarg.2
0x2d7f8  call     instance void InMember::WriteXmlSpaceOrThrow(class System.Xaml.XamlXmlWriter writer, string value)
0x2d7fd  ldarg.1
0x2d7fe  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d803  ldarg.2
0x2d804  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x2d809  ldarg.1
0x2d80a  call     class WriterState InMemberAfterValue::get_State()
0x2d80f  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d814  br       loc_2D8B7
0x2d819  ldstr    aWhitespaceinco// "WhiteSpaceInCollection"
0x2d81e  ldc.i4.2
0x2d81f  newarr   [mscorlib]System.Object
0x2d824  dup
0x2d825  ldc.i4.0
0x2d826  ldarg.2
0x2d827  stelem.ref
0x2d828  dup
0x2d829  ldc.i4.1
0x2d82a  ldloc.1
0x2d82b  callvirt instance string System.Xaml.XamlType::get_Name()
0x2d830  stelem.ref
0x2d831  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d836  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d83b  throw
0x2d83c  ldarg.2
0x2d83d  call     bool System.Xaml.XamlXmlWriter::ContainsLeadingSpace(string s)
0x2d842  brfalse.s loc_2D86B
0x2d844  ldarg.1
0x2d845  ldfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d84a  brfalse.s loc_2D86B
0x2d84c  ldarg.0
0x2d84d  ldarg.1
0x2d84e  ldarg.2
0x2d84f  call     instance void InMember::WriteXmlSpaceOrThrow(class System.Xaml.XamlXmlWriter writer, string value)
0x2d854  ldarg.1
0x2d855  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d85a  ldarg.2
0x2d85b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x2d860  ldarg.1
0x2d861  call     class WriterState InMemberAfterValue::get_State()
0x2d866  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d86b  ldarg.2
0x2d86c  call     bool System.Xaml.XamlXmlWriter::ContainsTrailingSpace(string s)
0x2d871  brfalse.s loc_2D887
0x2d873  ldarg.1
0x2d874  ldarg.2
0x2d875  stfld    string System.Xaml.XamlXmlWriter::deferredValue
0x2d87a  ldarg.1
0x2d87b  call     class WriterState InMemberAfterValueWithSignificantWhitespace::get_State()
0x2d880  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d885  br.s     loc_2D8B7
0x2d887  ldarg.1
0x2d888  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d88d  ldarg.2
0x2d88e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x2d893  ldarg.1
0x2d894  call     class WriterState InMemberAfterValue::get_State()
0x2d899  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d89e  br.s     loc_2D8B7
0x2d8a0  ldarg.1
0x2d8a1  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d8a6  ldarg.2
0x2d8a7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x2d8ac  ldarg.1
0x2d8ad  call     class WriterState InMemberAfterValue::get_State()
0x2d8b2  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d8b7  ldarg.1
0x2d8b8  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d8bd  call     class WriterState InMemberAfterValueWithSignificantWhitespace::get_State()
0x2d8c2  beq.s    loc_2D8CB
0x2d8c4  ldarg.1
0x2d8c5  ldc.i4.0
0x2d8c6  stfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d8cb  ret
```
