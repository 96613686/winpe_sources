# WriterState::WriteValue_0

- ea: `0x2cdd0`
- end: `0x2cdee`
- name: `WriterState::WriteValue_0`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf810`
- `0x2cfc0`
- `0x2dca0`
- `0x2e020`
- `0x2e140`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cddd`: `WriteValue`
- `0x2cdd0`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2cdd0  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cdd5  ldc.i4.1
0x2cdd6  newarr   [mscorlib]System.Object
0x2cddb  dup
0x2cddc  ldc.i4.0
0x2cddd  ldstr    aWritevalue// "WriteValue"
0x2cde2  stelem.ref
0x2cde3  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cde8  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cded  throw
```
