# __dllonexit_0

- ea: `0x180001bae`
- end: `0x180001bb4`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800018f4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001bae`

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
0x180001bae  jmp     cs:__imp___dllonexit
```
