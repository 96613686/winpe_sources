# SchemaReader::.ctor

- ea: `0x3a380`
- end: `0x3a39c`
- name: `SchemaReader::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x2d0e0`

## callees

- `0x3a380`

## string_xrefs

- `0x3a389`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x3a380  ldarg.0
0x3a381  call     instance void [mscorlib]System.Object::.ctor()
0x3a386  ldarg.1
0x3a387  brtrue.s loc_3A394
0x3a389  ldstr    aReader// "reader"
0x3a38e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3a393  throw
0x3a394  ldarg.0
0x3a395  ldarg.1
0x3a396  stfld    class [System.Data]System.Data.IDataReader SchemaReader::m_reader
0x3a39b  ret
```
