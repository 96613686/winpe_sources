# __dllonexit_0

- ea: `0x180001b0e`
- end: `0x180001b14`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001854`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001b0e`

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
0x180001b0e  jmp     cs:__imp___dllonexit
```
