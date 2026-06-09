# RSWPTraceInternal::Fail

- ea: `0x16970`
- end: `0x16983`
- name: `RSWPTraceInternal::Fail`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x174c0`

## string_xrefs

- `0x16972`: `Un-named assertion fired for component `

## pseudocode

```c

```

## disassembly

```asm
0x16970  ldarg.0
0x16971  ldarg.1
0x16972  ldstr    aUnNamedAsserti_0// "Un-named assertion fired for component "
0x16977  ldarg.1
0x16978  call     string [mscorlib]System.String::Concat(string, string)
0x1697d  call     instance void RSWPTraceInternal::FailInternal(string componentName, string message)
0x16982  ret
```
