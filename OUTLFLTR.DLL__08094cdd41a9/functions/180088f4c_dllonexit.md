# __dllonexit

- ea: `0x180088f4c`
- end: `0x180088f52`
- name: `__dllonexit`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800888c0`

## import_xrefs

- `MSVCR90!__dllonexit` at `0x180088f4c`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit()
{
  return __dllonexit();
}

```

## disassembly

```asm
0x180088f4c  jmp     cs:__imp___dllonexit
```
