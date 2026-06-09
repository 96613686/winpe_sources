# __dllonexit_0

- ea: `0x1400021ee`
- end: `0x1400021f4`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001ba8`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1400021ee`

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
0x1400021ee  jmp     cs:__imp___dllonexit
```
