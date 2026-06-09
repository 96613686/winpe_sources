# System.Xaml.WriterDelegate::ThrowBecauseWriterIsClosed2

- ea: `0x6f40`
- end: `0x6f50`
- name: `System.Xaml.WriterDelegate::ThrowBecauseWriterIsClosed2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x8440`
- `0x11f20`

## string_xrefs

- `0x6f40`: `WriterIsClosed`

## pseudocode

```c

```

## disassembly

```asm
0x6f40  ldstr    aWriterisclosed// "WriterIsClosed"
0x6f45  call     string System.Xaml.SR::Get(string id)
0x6f4a  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x6f4f  throw
```
