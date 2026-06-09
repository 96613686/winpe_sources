# __dllonexit_0

- ea: `0x18000a56e`
- end: `0x18000a574`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000a058`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000a56e`

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
0x18000a56e  jmp     cs:__imp___dllonexit
```
