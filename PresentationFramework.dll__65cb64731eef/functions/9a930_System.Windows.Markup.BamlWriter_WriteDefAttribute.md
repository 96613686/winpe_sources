# System.Windows.Markup.BamlWriter::WriteDefAttribute

- ea: `0x9a930`
- end: `0x9aacc`
- name: `System.Windows.Markup.BamlWriter::WriteDefAttribute`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x213510`

## callees

- `0x38c70`
- `0x94650`
- `0x94800`
- `0x9a930`
- `0x9b0e0`
- `0x9b3c0`
- `0x9b3e0`
- `0xab5c0`
- `0xab640`
- `0xabfb0`
- `0xad120`
- `0xb0ee0`
- `0xb0f50`
- `0xb4030`

## string_xrefs

- `0x9a94e`: `BamlWriterNoInElement`
- `0x9a95b`: `WriteDefAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x9a930  ldarg.0
0x9a931  call     instance void System.Windows.Markup.BamlWriter::VerifyWriteState()
0x9a936  ldarg.0
0x9a937  call     instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlWriter::PeekRecordType()
0x9a93c  stloc.0
0x9a93d  ldloc.0
0x9a93e  ldc.i4.3
0x9a93f  beq.s    loc_9A97C
0x9a941  ldarg.1
0x9a942  ldstr    aUid// "Uid"
0x9a947  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9a94c  brfalse.s loc_9A97C
0x9a94e  ldstr    aBamlwriternoin// "BamlWriterNoInElement"
0x9a953  ldc.i4.2
0x9a954  newarr   [mscorlib]System.Object
0x9a959  dup
0x9a95a  ldc.i4.0
0x9a95b  ldstr    aWritedefattrib// "WriteDefAttribute"
0x9a960  stelem.ref
0x9a961  dup
0x9a962  ldc.i4.1
0x9a963  ldloca.s 0
0x9a965  constrained. System.Windows.Markup.BamlRecordType
0x9a96b  callvirt instance string [mscorlib]System.Object::ToString()
0x9a970  stelem.ref
0x9a971  call     string System.Windows.SR::Get(string id, object[] args)
0x9a976  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a97b  throw
0x9a97c  ldarg.1
0x9a97d  ldstr    aKey// "Key"
0x9a982  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a987  brfalse  loc_9AAAF
0x9a98c  ldarg.0
0x9a98d  ldfld    class System.Windows.Markup.MarkupExtensionParser System.Windows.Markup.BamlWriter::_extensionParser
0x9a992  ldarg.0
0x9a993  call     instance class [mscorlib]System.Type System.Windows.Markup.BamlWriter::PeekElementType()
0x9a998  ldarga.s 2
0x9a99a  ldc.i4.0
0x9a99b  ldc.i4.0
0x9a99c  ldc.i4.0
0x9a99d  callvirt instance class System.Windows.Markup.DefAttributeData System.Windows.Markup.MarkupExtensionParser::IsMarkupExtensionDefAttribute(class [mscorlib]System.Type declaringType, string& attrValue, int32 lineNumber, int32 linePosition, int32 depth)
0x9a9a2  stloc.2
0x9a9a3  ldloc.2
0x9a9a4  brfalse  loc_9AAAF
0x9a9a9  ldarg.1
0x9a9aa  ldstr    aKey// "Key"
0x9a9af  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9a9b4  brfalse.s loc_9A9BD
0x9a9b6  ldloc.2
0x9a9b7  ldc.i4.0
0x9a9b8  stfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0x9a9bd  ldloc.2
0x9a9be  ldfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0x9a9c3  brfalse  loc_9AA94
0x9a9c8  ldloc.2
0x9a9c9  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a9ce  ldc.i4.s 0x3A
0x9a9d0  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x9a9d5  stloc.3
0x9a9d6  ldsfld   string [mscorlib]System.String::Empty
0x9a9db  stloc.s  4
0x9a9dd  ldloc.2
0x9a9de  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a9e3  stloc.s  5
0x9a9e5  ldloc.3
0x9a9e6  ldc.i4.0
0x9a9e7  ble.s    loc_9AA08
0x9a9e9  ldloc.2
0x9a9ea  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a9ef  ldc.i4.0
0x9a9f0  ldloc.3
0x9a9f1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x9a9f6  stloc.s  4
0x9a9f8  ldloc.2
0x9a9f9  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a9fe  ldloc.3
0x9a9ff  ldc.i4.1
0x9aa00  add
0x9aa01  callvirt instance string [mscorlib]System.String::Substring(int32)
0x9aa06  stloc.s  5
0x9aa08  ldarg.0
0x9aa09  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlWriter::_parserContext
0x9aa0e  callvirt instance class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.ParserContext::get_XmlnsDictionary()
0x9aa13  ldloc.s  4
0x9aa15  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x9aa1a  stloc.s  6
0x9aa1c  ldsfld   string [mscorlib]System.String::Empty
0x9aa21  stloc.s  7
0x9aa23  ldsfld   string [mscorlib]System.String::Empty
0x9aa28  stloc.s  8
0x9aa2a  ldnull
0x9aa2b  stloc.s  9
0x9aa2d  ldnull
0x9aa2e  stloc.s  0xA
0x9aa30  ldarg.0
0x9aa31  ldc.i4.0
0x9aa32  ldloc.s  5
0x9aa34  ldloc.s  6
0x9aa36  ldloca.s 7
0x9aa38  ldloca.s 8
0x9aa3a  ldloca.s 9
0x9aa3c  ldloca.s 0xA
0x9aa3e  callvirt instance bool System.Windows.Markup.IParserHelper::GetElementType(bool extensionFirst, string localName, string namespaceURI, string& assemblyName, string& typeFullName, class [mscorlib]System.Type& baseType, class [mscorlib]System.Type& serializerType)
0x9aa43  stloc.s  0xB
0x9aa45  ldloc.s  0xB
0x9aa47  brfalse.s loc_9AA77
0x9aa49  ldc.i4.0
0x9aa4a  ldc.i4.0
0x9aa4b  ldarg.0
0x9aa4c  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9aa51  ldloc.s  8
0x9aa53  ldloc.s  9
0x9aa55  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9aa5a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x9aa5f  ldloc.s  9
0x9aa61  newobj   instance void System.Windows.Markup.XamlDefAttributeKeyTypeNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, string value, string assemblyName, class [mscorlib]System.Type valueType)
0x9aa66  stloc.s  0xC
0x9aa68  ldarg.0
0x9aa69  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9aa6e  ldloc.s  0xC
0x9aa70  callvirt instance void System.Windows.Markup.BamlRecordWriter::WriteDefAttributeKeyType(class System.Windows.Markup.XamlDefAttributeKeyTypeNode xamlDefNode)
0x9aa75  br.s     loc_9AA94
0x9aa77  ldloc.2
0x9aa78  ldc.i4.0
0x9aa79  stfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0x9aa7e  ldloc.2
0x9aa7f  dup
0x9aa80  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9aa85  ldstr    asc_29CBC0// "}"
0x9aa8a  call     string [mscorlib]System.String::Concat(string, string)
0x9aa8f  stfld    string System.Windows.Markup.DefAttributeData::Args
0x9aa94  ldloc.2
0x9aa95  ldfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0x9aa9a  brtrue.s loc_9AAAE
0x9aa9c  ldarg.0
0x9aa9d  ldfld    class System.Windows.Markup.MarkupExtensionParser System.Windows.Markup.BamlWriter::_extensionParser
0x9aaa2  ldarg.0
0x9aaa3  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Markup.BamlWriter::_markupExtensionNodes
0x9aaa8  ldloc.2
0x9aaa9  callvirt instance void System.Windows.Markup.MarkupExtensionParser::CompileDictionaryKey(class [mscorlib]System.Collections.ArrayList xamlNodes, class System.Windows.Markup.DefAttributeData data)
0x9aaae  ret
0x9aaaf  ldc.i4.0
0x9aab0  ldc.i4.0
0x9aab1  ldarg.0
0x9aab2  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9aab7  ldarg.1
0x9aab8  ldarg.2
0x9aab9  newobj   instance void System.Windows.Markup.XamlDefAttributeNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, string name, string value)
0x9aabe  stloc.1
0x9aabf  ldarg.0
0x9aac0  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9aac5  ldloc.1
0x9aac6  callvirt instance void System.Windows.Markup.BamlRecordWriter::WriteDefAttribute(class System.Windows.Markup.XamlDefAttributeNode xamlDefNode)
0x9aacb  ret
```
