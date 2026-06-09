# __dllonexit_0

- ea: `0x180001bed`
- end: `0x180001bf3`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001b10`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001bed`

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
0x180001bed  jmp     cs:__imp___dllonexit
```
