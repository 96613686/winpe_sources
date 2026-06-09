# WriterState::WriteEndObject_0

- ea: `0x2cd70`
- end: `0x2cd8e`
- name: `WriterState::WriteEndObject_0`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf770`
- `0x2cfc0`
- `0x2d680`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cd7d`: `WriteEndObject`
- `0x2cd70`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2cd70  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cd75  ldc.i4.1
0x2cd76  newarr   [mscorlib]System.Object
0x2cd7b  dup
0x2cd7c  ldc.i4.0
0x2cd7d  ldstr    aWriteendobject// "WriteEndObject"
0x2cd82  stelem.ref
0x2cd83  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cd88  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cd8d  throw
```
