# __dllonexit_0

- ea: `0x180001d0c`
- end: `0x180001d12`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000191c`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001d0c`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit_0()
{
  return __dllonexit();
}

```

## disassembly

```asm
0x180001d0c  jmp     cs:__imp___dllonexit
```
