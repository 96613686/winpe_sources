# System.Xaml.ReaderDelegate::Read

- ea: `0x6b20`
- end: `0x6b97`
- name: `System.Xaml.ReaderDelegate::Read`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x2040`
- `0x20d0`
- `0x22f0`
- `0x2310`
- `0x2350`
- `0x6b20`
- `0xb330`
- `0xb3f0`

## string_xrefs

- `0x6b28`: `XamlReader`

## pseudocode

```c

```

## disassembly

```asm
0x6b20  ldarg.0
0x6b21  call     instance bool System.Xaml.XamlReader::get_IsDisposed()
0x6b26  brfalse.s loc_6B33
0x6b28  ldstr    aXamlreader// "XamlReader"
0x6b2d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x6b32  throw
0x6b33  ldarg.0
0x6b34  ldarg.0
0x6b35  ldfld    class System.Xaml.XamlNodeNextDelegate System.Xaml.ReaderDelegate::_nextDelegate
0x6b3a  callvirt instance valuetype System.Xaml.XamlNode System.Xaml.XamlNodeNextDelegate::Invoke()
0x6b3f  stfld    valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b44  ldarg.0
0x6b45  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b4a  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x6b4f  brfalse.s loc_6B53
0x6b51  ldc.i4.1
0x6b52  ret
0x6b53  ldarg.0
0x6b54  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b59  call     instance bool System.Xaml.XamlNode::get_IsLineInfo()
0x6b5e  brfalse.s loc_6B73
0x6b60  ldarg.0
0x6b61  ldarg.0
0x6b62  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b67  call     instance class System.Xaml.LineInfo System.Xaml.XamlNode::get_LineInfo()
0x6b6c  stfld    class System.Xaml.LineInfo System.Xaml.ReaderBaseDelegate::_currentLineInfo
0x6b71  br.s     loc_6B80
0x6b73  ldarg.0
0x6b74  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b79  call     instance bool System.Xaml.XamlNode::get_IsEof()
0x6b7e  brtrue.s loc_6B8D
0x6b80  ldarg.0
0x6b81  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6b86  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x6b8b  brfalse.s loc_6B33
0x6b8d  ldarg.0
0x6b8e  callvirt instance bool System.Xaml.XamlReader::get_IsEof()
0x6b93  ldc.i4.0
0x6b94  ceq
0x6b96  ret
```
