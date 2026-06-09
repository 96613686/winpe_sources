# __dllonexit_0

- ea: `0x1800021ab`
- end: `0x1800021b1`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001cb4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800021ab`

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
0x1800021ab  jmp     cs:__imp___dllonexit
```
