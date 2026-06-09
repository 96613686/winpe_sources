# __current_exception_context_0

- ea: `0x140002748`
- end: `0x14000274e`
- name: `__current_exception_context_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000202c`
- `0x1400023a0`

## import_xrefs

- `VCRUNTIME140!__current_exception_context` at `0x140002748`

## pseudocode

```c
// attributes: thunk
__int64 _current_exception_context_0()
{
  return __current_exception_context();
}

```

## disassembly

```asm
0x140002748  jmp     cs:__imp___current_exception_context
```
