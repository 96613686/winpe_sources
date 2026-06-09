# __current_exception_0

- ea: `0x140002742`
- end: `0x140002748`
- name: `__current_exception_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000202c`
- `0x1400023a0`

## import_xrefs

- `VCRUNTIME140!__current_exception` at `0x140002742`

## pseudocode

```c
// attributes: thunk
__int64 _current_exception_0()
{
  return __current_exception();
}

```

## disassembly

```asm
0x140002742  jmp     cs:__imp___current_exception
```
