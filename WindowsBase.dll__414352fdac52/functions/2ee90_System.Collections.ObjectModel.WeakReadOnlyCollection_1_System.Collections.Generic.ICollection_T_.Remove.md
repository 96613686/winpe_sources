# System.Collections.ObjectModel.WeakReadOnlyCollection`1::System.Collections.Generic.ICollection<T>.Remove

- ea: `0x2ee90`
- end: `0x2eea0`
- name: `System.Collections.ObjectModel.WeakReadOnlyCollection`1::System.Collections.Generic.ICollection<T>.Remove`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x2c100`

## string_xrefs

- `0x2ee90`: `NotSupported_ReadOnlyCollection`

## pseudocode

```c

```

## disassembly

```asm
0x2ee90  ldstr    aNotsupportedRe// "NotSupported_ReadOnlyCollection"
0x2ee95  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2ee9a  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2ee9f  throw
```
