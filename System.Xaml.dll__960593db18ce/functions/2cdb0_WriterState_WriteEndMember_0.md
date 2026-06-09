# WriterState::WriteEndMember_0

- ea: `0x2cdb0`
- end: `0x2cdce`
- name: `WriterState::WriteEndMember_0`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf7f0`
- `0x2cfc0`
- `0x2dba0`
- `0x2dcc0`
- `0x2df50`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cdbd`: `WriteEndMember`
- `0x2cdb0`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2cdb0  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cdb5  ldc.i4.1
0x2cdb6  newarr   [mscorlib]System.Object
0x2cdbb  dup
0x2cdbc  ldc.i4.0
0x2cdbd  ldstr    aWriteendmember// "WriteEndMember"
0x2cdc2  stelem.ref
0x2cdc3  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cdc8  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cdcd  throw
```
