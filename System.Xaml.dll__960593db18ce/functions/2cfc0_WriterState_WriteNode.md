# WriterState::WriteNode

- ea: `0x2cfc0`
- end: `0x2d0a6`
- name: `WriterState::WriteNode`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x2e250`
- `0x2e7b0`

## callees

- `0x20d0`
- `0x2270`
- `0x2290`
- `0x22b0`
- `0x22d0`
- `0xa590`
- `0x11f20`
- `0x2cb30`
- `0x2cb70`
- `0x2cd50`
- `0x2cd70`
- `0x2cd90`
- `0x2cdb0`
- `0x2cdd0`
- `0x2cdf0`
- `0x2cfc0`

## pseudocode

```c

```

## disassembly

```asm
0x2cfc0  ldarga.s 2
0x2cfc2  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x2cfc7  stloc.2
0x2cfc8  ldloc.2
0x2cfc9  switch   loc_2D0A5, loc_2D007, loc_2D01C, loc_2D04E, loc_2D05B, loc_2D06F, loc_2D07C, loc_2CFF3
0x2cfee  br       loc_2D095
0x2cff3  ldarg.1
0x2cff4  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2cff9  ldarg.1
0x2cffa  ldarga.s 2
0x2cffc  call     instance class System.Xaml.NamespaceDeclaration System.Xaml.XamlNode::get_NamespaceDeclaration()
0x2d001  callvirt instance void WriterState::WriteNamespace(class System.Xaml.XamlXmlWriter writer, class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0x2d006  ret
0x2d007  ldarg.1
0x2d008  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d00d  ldarg.1
0x2d00e  ldarga.s 2
0x2d010  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x2d015  ldc.i4.0
0x2d016  callvirt instance void WriterState::WriteObject(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlType type, bool isObjectFromMember)
0x2d01b  ret
0x2d01c  ldnull
0x2d01d  stloc.0
0x2d01e  ldarg.1
0x2d01f  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d024  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d029  stloc.1
0x2d02a  ldloc.1
0x2d02b  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d030  ldc.i4.4
0x2d031  bne.un.s loc_2D03F
0x2d033  ldloc.1
0x2d034  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2d039  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2d03e  stloc.0
0x2d03f  ldarg.1
0x2d040  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d045  ldarg.1
0x2d046  ldloc.0
0x2d047  ldc.i4.1
0x2d048  callvirt instance void WriterState::WriteObject(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlType type, bool isObjectFromMember)
0x2d04d  ret
0x2d04e  ldarg.1
0x2d04f  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d054  ldarg.1
0x2d055  callvirt instance void WriterState::WriteEndObject(class System.Xaml.XamlXmlWriter writer)
0x2d05a  ret
0x2d05b  ldarg.1
0x2d05c  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d061  ldarg.1
0x2d062  ldarga.s 2
0x2d064  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x2d069  callvirt instance void WriterState::WriteStartMember(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlMember property)
0x2d06e  ret
0x2d06f  ldarg.1
0x2d070  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d075  ldarg.1
0x2d076  callvirt instance void WriterState::WriteEndMember(class System.Xaml.XamlXmlWriter writer)
0x2d07b  ret
0x2d07c  ldarg.1
0x2d07d  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d082  ldarg.1
0x2d083  ldarga.s 2
0x2d085  call     instance object System.Xaml.XamlNode::get_Value()
0x2d08a  isinst   [mscorlib]System.String
0x2d08f  callvirt instance void WriterState::WriteValue(class System.Xaml.XamlXmlWriter writer, string value)
0x2d094  ret
0x2d095  ldstr    aMissingcasexam// "MissingCaseXamlNodes"
0x2d09a  call     string System.Xaml.SR::Get(string id)
0x2d09f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2d0a4  throw
0x2d0a5  ret
```
