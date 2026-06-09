# __dllonexit_0

- ea: `0x18000202e`
- end: `0x180002034`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001af4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000202e`

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
0x18000202e  jmp     cs:__imp___dllonexit
```
