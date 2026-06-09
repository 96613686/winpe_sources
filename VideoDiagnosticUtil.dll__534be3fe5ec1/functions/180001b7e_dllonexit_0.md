# __dllonexit_0

- ea: `0x180001b7e`
- end: `0x180001b84`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016c4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001b7e`

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
0x180001b7e  jmp     cs:__imp___dllonexit
```
