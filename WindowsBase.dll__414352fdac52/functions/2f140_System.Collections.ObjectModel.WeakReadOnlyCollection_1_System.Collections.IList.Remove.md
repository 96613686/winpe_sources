# System.Collections.ObjectModel.WeakReadOnlyCollection`1::System.Collections.IList.Remove

- ea: `0x2f140`
- end: `0x2f150`
- name: `System.Collections.ObjectModel.WeakReadOnlyCollection`1::System.Collections.IList.Remove`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x2c100`

## string_xrefs

- `0x2f140`: `NotSupported_ReadOnlyCollection`

## pseudocode

```c

```

## disassembly

```asm
0x2f140  ldstr    aNotsupportedRe// "NotSupported_ReadOnlyCollection"
0x2f145  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2f14a  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2f14f  throw
```
