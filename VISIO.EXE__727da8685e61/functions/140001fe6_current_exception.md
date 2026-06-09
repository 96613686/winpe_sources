# __current_exception

- ea: `0x140001fe6`
- end: `0x140001fec`
- name: `__current_exception`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d90`

## import_xrefs

- `VCRUNTIME140!__current_exception` at `0x140001fe6`

## pseudocode

```c
// attributes: thunk
__int64 _current_exception()
{
  return __current_exception();
}

```

## disassembly

```asm
0x140001fe6  jmp     cs:__imp___current_exception
```
