# WriterState::WriteStartMember_0

- ea: `0x2cd90`
- end: `0x2cdae`
- name: `WriterState::WriteStartMember_0`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf790`
- `0x2cfc0`
- `0x2d4c0`

## callees

- `0x8860`
- `0x11f50`

## string_xrefs

- `0x2cd90`: `XamlXmlWriterWriteNotSupportedInCurrentState`
- `0x2cd9d`: `WriteStartMember`

## pseudocode

```c

```

## disassembly

```asm
0x2cd90  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2cd95  ldc.i4.1
0x2cd96  newarr   [mscorlib]System.Object
0x2cd9b  dup
0x2cd9c  ldc.i4.0
0x2cd9d  ldstr    aWritestartmemb// "WriteStartMember"
0x2cda2  stelem.ref
0x2cda3  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cda8  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cdad  throw
```
