# WriterState::WriteNamespace_0

- ea: `0x2cdf0`
- end: `0x2ce0e`
- name: `WriterState::WriteNamespace_0`
- size: `30`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf860`
- `0xfec0`
- `0x2cfc0`
- `0x2d4a0`
- `0x2dac0`
- `0x2db80`
- `0x2dc80`
- `0x2ddf0`
- `0x2df10`
- `0x2dff0`
- `0x2e100`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cdfd`: `WriteNamespace`
- `0x2cdf0`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2cdf0  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cdf5  ldc.i4.1
0x2cdf6  newarr   [mscorlib]System.Object
0x2cdfb  dup
0x2cdfc  ldc.i4.0
0x2cdfd  ldstr    aWritenamespace// "WriteNamespace"
0x2ce02  stelem.ref
0x2ce03  call     string System.Xaml.SR::Get(string id, object[] args)
0x2ce08  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2ce0d  throw
```
