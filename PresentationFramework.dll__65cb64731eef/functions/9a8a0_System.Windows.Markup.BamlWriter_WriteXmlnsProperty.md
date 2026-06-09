# System.Windows.Markup.BamlWriter::WriteXmlnsProperty

- ea: `0x9a8a0`
- end: `0x9a921`
- name: `System.Windows.Markup.BamlWriter::WriteXmlnsProperty`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x213080`

## callees

- `0x38c70`
- `0x94a80`
- `0x9a8a0`
- `0x9b0e0`
- `0x9b3c0`
- `0xad120`
- `0xb0cb0`
- `0xb4040`

## string_xrefs

- `0x9a8c4`: `BamlWriterBadXmlns`
- `0x9a8d1`: `WriteXmlnsProperty`

## pseudocode

```c

```

## disassembly

```asm
0x9a8a0  ldarg.0
0x9a8a1  call     instance void System.Windows.Markup.BamlWriter::VerifyWriteState()
0x9a8a6  ldarg.0
0x9a8a7  call     instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlWriter::PeekRecordType()
0x9a8ac  stloc.0
0x9a8ad  ldloc.0
0x9a8ae  ldc.i4.3
0x9a8af  beq.s    loc_9A8F2
0x9a8b1  ldloc.0
0x9a8b2  ldc.i4.7
0x9a8b3  beq.s    loc_9A8F2
0x9a8b5  ldloc.0
0x9a8b6  ldc.i4.s 9
0x9a8b8  beq.s    loc_9A8F2
0x9a8ba  ldloc.0
0x9a8bb  ldc.i4.s 0xB
0x9a8bd  beq.s    loc_9A8F2
0x9a8bf  ldloc.0
0x9a8c0  ldc.i4.s 0xD
0x9a8c2  beq.s    loc_9A8F2
0x9a8c4  ldstr    aBamlwriterbadx// "BamlWriterBadXmlns"
0x9a8c9  ldc.i4.2
0x9a8ca  newarr   [mscorlib]System.Object
0x9a8cf  dup
0x9a8d0  ldc.i4.0
0x9a8d1  ldstr    aWritexmlnsprop// "WriteXmlnsProperty"
0x9a8d6  stelem.ref
0x9a8d7  dup
0x9a8d8  ldc.i4.1
0x9a8d9  ldloca.s 0
0x9a8db  constrained. System.Windows.Markup.BamlRecordType
0x9a8e1  callvirt instance string [mscorlib]System.Object::ToString()
0x9a8e6  stelem.ref
0x9a8e7  call     string System.Windows.SR::Get(string id, object[] args)
0x9a8ec  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a8f1  throw
0x9a8f2  ldc.i4.0
0x9a8f3  ldc.i4.0
0x9a8f4  ldarg.0
0x9a8f5  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9a8fa  ldarg.1
0x9a8fb  ldarg.2
0x9a8fc  newobj   instance void System.Windows.Markup.XamlXmlnsPropertyNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, string prefix, string xmlNamespace)
0x9a901  stloc.1
0x9a902  ldarg.0
0x9a903  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a908  ldloc.1
0x9a909  callvirt instance void System.Windows.Markup.BamlRecordWriter::WriteNamespacePrefix(class System.Windows.Markup.XamlXmlnsPropertyNode xamlXmlnsPropertyNode)
0x9a90e  ldarg.0
0x9a90f  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlWriter::_parserContext
0x9a914  callvirt instance class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.ParserContext::get_XmlnsDictionary()
0x9a919  ldarg.1
0x9a91a  ldarg.2
0x9a91b  callvirt instance void System.Windows.Markup.XmlnsDictionary::set_Item(string prefix, string value)
0x9a920  ret
```
