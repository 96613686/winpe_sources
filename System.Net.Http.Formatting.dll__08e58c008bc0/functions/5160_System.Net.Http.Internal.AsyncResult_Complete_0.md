# System.Net.Http.Internal.AsyncResult::Complete_0

- ea: `0x5160`
- end: `0x516f`
- name: `System.Net.Http.Internal.AsyncResult::Complete_0`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4910`
- `0x4960`

## callees

- `0x5100`

## pseudocode

```c

```

## disassembly

```asm
0x5160  ldarg.0
0x5161  ldarg.2
0x5162  stfld    class [mscorlib]System.Exception System.Net.Http.Internal.AsyncResult::_exception
0x5167  ldarg.0
0x5168  ldarg.1
0x5169  call     instance void System.Net.Http.Internal.AsyncResult::Complete(bool completedSynchronously)
0x516e  ret
```
