# __dllonexit_0

- ea: `0x180001ba1`
- end: `0x180001ba7`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ad0`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001ba1`

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
0x180001ba1  jmp     cs:__imp___dllonexit
```
