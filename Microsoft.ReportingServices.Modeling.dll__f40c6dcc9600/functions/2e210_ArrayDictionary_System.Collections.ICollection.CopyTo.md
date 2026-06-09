# ArrayDictionary::System.Collections.ICollection.CopyTo

- ea: `0x2e210`
- end: `0x2e21b`
- name: `ArrayDictionary::System.Collections.ICollection.CopyTo`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x97d0`

## string_xrefs

- `0x2e210`: `CopyTo is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x2e210  ldstr    aCopytoIsNotSup// "CopyTo is not supported."
0x2e215  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2e21a  throw
```
