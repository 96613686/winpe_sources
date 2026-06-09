# System.Net.Http.Formatting.MediaTypeFormatterCollection::CreateDefaultFormatters

- ea: `0x8640`
- end: `0x865f`
- name: `System.Net.Http.Formatting.MediaTypeFormatterCollection::CreateDefaultFormatters`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x8270`

## callees

- `0x7440`
- `0x7740`
- `0x9000`

## pseudocode

```c

```

## disassembly

```asm
0x8640  ldc.i4.3
0x8641  newarr   System.Net.Http.Formatting.MediaTypeFormatter
0x8646  dup
0x8647  ldc.i4.0
0x8648  newobj   instance void System.Net.Http.Formatting.JsonMediaTypeFormatter::.ctor()
0x864d  stelem.ref
0x864e  dup
0x864f  ldc.i4.1
0x8650  newobj   instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::.ctor()
0x8655  stelem.ref
0x8656  dup
0x8657  ldc.i4.2
0x8658  newobj   instance void System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::.ctor()
0x865d  stelem.ref
0x865e  ret
```
