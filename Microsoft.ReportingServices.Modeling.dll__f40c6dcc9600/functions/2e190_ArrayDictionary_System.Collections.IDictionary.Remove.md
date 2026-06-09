# ArrayDictionary::System.Collections.IDictionary.Remove

- ea: `0x2e190`
- end: `0x2e19b`
- name: `ArrayDictionary::System.Collections.IDictionary.Remove`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x97d0`

## string_xrefs

- `0x2e190`: `Remove is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x2e190  ldstr    aRemoveIsNotSup// "Remove is not supported."
0x2e195  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x2e19a  throw
```
