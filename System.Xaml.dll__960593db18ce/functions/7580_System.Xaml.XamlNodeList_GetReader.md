# System.Xaml.XamlNodeList::GetReader

- ea: `0x7580`
- end: `0x75e3`
- name: `System.Xaml.XamlNodeList::GetReader`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x2ca0`
- `0x3690`

## callees

- `0x2080`
- `0x6bf0`
- `0x7580`
- `0x8440`
- `0xf3b0`
- `0x11f20`

## string_xrefs

- `0x7588`: `CloseXamlWriterBeforeReading`

## pseudocode

```c

```

## disassembly

```asm
0x7580  ldarg.0
0x7581  ldfld    bool System.Xaml.XamlNodeList::_readMode
0x7586  brtrue.s loc_7598
0x7588  ldstr    aClosexamlwrite// "CloseXamlWriterBeforeReading"
0x758d  call     string System.Xaml.SR::Get(string id)
0x7592  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x7597  throw
0x7598  ldarg.0
0x7599  ldfld    class System.Xaml.XamlWriter System.Xaml.XamlNodeList::_writer
0x759e  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0x75a3  brtrue.s loc_75B5
0x75a5  ldstr    aSchemacontextn// "SchemaContextNotInitialized"
0x75aa  call     string System.Xaml.SR::Get(string id)
0x75af  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x75b4  throw
0x75b5  ldarg.0
0x75b6  ldfld    class System.Xaml.XamlWriter System.Xaml.XamlNodeList::_writer
0x75bb  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0x75c0  ldarg.0
0x75c1  ldftn    instance valuetype System.Xaml.XamlNode System.Xaml.XamlNodeList::Index(int32 idx)
0x75c7  newobj   instance void System.Xaml.XamlNodeIndexDelegate::.ctor(object object, native int method)
0x75cc  ldarg.0
0x75cd  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> System.Xaml.XamlNodeList::_nodeList
0x75d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::get_Count()
0x75d7  ldarg.0
0x75d8  ldfld    bool System.Xaml.XamlNodeList::_hasLineInfo
0x75dd  newobj   instance void System.Xaml.ReaderMultiIndexDelegate::.ctor(class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlNodeIndexDelegate indexDelegate, int32 count, bool hasLineInfo)
0x75e2  ret
```
