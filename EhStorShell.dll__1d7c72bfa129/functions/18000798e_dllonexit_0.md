# __dllonexit_0

- ea: `0x18000798e`
- end: `0x180007994`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800074c4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000798e`

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
0x18000798e  jmp     cs:__imp___dllonexit
```
