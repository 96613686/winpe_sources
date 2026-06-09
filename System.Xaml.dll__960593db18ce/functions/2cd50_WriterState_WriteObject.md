# WriterState::WriteObject

- ea: `0x2cd50`
- end: `0x2cd6e`
- name: `WriterState::WriteObject`
- size: `30`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf6c0`
- `0xf700`
- `0x2cfc0`
- `0x2db20`
- `0x2dc10`
- `0x2dce0`
- `0x2de50`
- `0x2df70`
- `0x2e090`
- `0x2e1d0`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cd50`: `XamlXmlWriterWriteNotSupportedInCurrentState`
- `0x2cd5d`: `WriteObject`

## pseudocode

```c

```

## disassembly

```asm
0x2cd50  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cd55  ldc.i4.1
0x2cd56  newarr   [mscorlib]System.Object
0x2cd5b  dup
0x2cd5c  ldc.i4.0
0x2cd5d  ldstr    aWriteobject// "WriteObject"
0x2cd62  stelem.ref
0x2cd63  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cd68  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cd6d  throw
```
