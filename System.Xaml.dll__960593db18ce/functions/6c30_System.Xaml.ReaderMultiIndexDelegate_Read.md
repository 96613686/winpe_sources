# System.Xaml.ReaderMultiIndexDelegate::Read

- ea: `0x6c30`
- end: `0x6ced`
- name: `System.Xaml.ReaderMultiIndexDelegate::Read`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2090`
- `0x20d0`
- `0x22f0`
- `0x2310`
- `0x6c30`
- `0xb330`
- `0xb3f0`

## string_xrefs

- `0x6c38`: `XamlReader`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  ldarg.0
0x6c31  call     instance bool System.Xaml.XamlReader::get_IsDisposed()
0x6c36  brfalse.s loc_6C43
0x6c38  ldstr    aXamlreader// "XamlReader"
0x6c3d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x6c42  throw
0x6c43  ldarg.0
0x6c44  ldfld    int32 System.Xaml.ReaderMultiIndexDelegate::_idx
0x6c49  ldarg.0
0x6c4a  ldfld    int32 System.Xaml.ReaderMultiIndexDelegate::_count
0x6c4f  ldc.i4.1
0x6c50  sub
0x6c51  bge.s    loc_6CB3
0x6c53  ldarg.0
0x6c54  ldarg.0
0x6c55  ldfld    class System.Xaml.XamlNodeIndexDelegate System.Xaml.ReaderMultiIndexDelegate::_indexDelegate
0x6c5a  ldarg.0
0x6c5b  ldarg.0
0x6c5c  ldfld    int32 System.Xaml.ReaderMultiIndexDelegate::_idx
0x6c61  ldc.i4.1
0x6c62  add
0x6c63  stloc.0
0x6c64  ldloc.0
0x6c65  stfld    int32 System.Xaml.ReaderMultiIndexDelegate::_idx
0x6c6a  ldloc.0
0x6c6b  callvirt instance valuetype System.Xaml.XamlNode System.Xaml.XamlNodeIndexDelegate::Invoke(int32 idx)
0x6c70  stfld    valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6c75  ldarg.0
0x6c76  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6c7b  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x6c80  brfalse.s loc_6C84
0x6c82  ldc.i4.1
0x6c83  ret
0x6c84  ldarg.0
0x6c85  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6c8a  call     instance class System.Xaml.LineInfo System.Xaml.XamlNode::get_LineInfo()
0x6c8f  brfalse.s loc_6CA4
0x6c91  ldarg.0
0x6c92  ldarg.0
0x6c93  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6c98  call     instance class System.Xaml.LineInfo System.Xaml.XamlNode::get_LineInfo()
0x6c9d  stfld    class System.Xaml.LineInfo System.Xaml.ReaderBaseDelegate::_currentLineInfo
0x6ca2  br.s     loc_6CD3
0x6ca4  ldarg.0
0x6ca5  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6caa  call     instance bool System.Xaml.XamlNode::get_IsEof()
0x6caf  brfalse.s loc_6CD3
0x6cb1  br.s     loc_6CE3
0x6cb3  ldarg.0
0x6cb4  ldarg.0
0x6cb5  ldfld    int32 System.Xaml.ReaderMultiIndexDelegate::_count
0x6cba  stfld    int32 System.Xaml.ReaderMultiIndexDelegate::_idx
0x6cbf  ldarg.0
0x6cc0  ldsfld   valuetype System.Xaml.XamlNode System.Xaml.ReaderMultiIndexDelegate::s_EndOfStream
0x6cc5  stfld    valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6cca  ldarg.0
0x6ccb  ldnull
0x6ccc  stfld    class System.Xaml.LineInfo System.Xaml.ReaderBaseDelegate::_currentLineInfo
0x6cd1  br.s     loc_6CE3
0x6cd3  ldarg.0
0x6cd4  ldflda   valuetype System.Xaml.XamlNode System.Xaml.ReaderBaseDelegate::_currentNode
0x6cd9  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x6cde  brfalse  loc_6C43
0x6ce3  ldarg.0
0x6ce4  callvirt instance bool System.Xaml.XamlReader::get_IsEof()
0x6ce9  ldc.i4.0
0x6cea  ceq
0x6cec  ret
```
