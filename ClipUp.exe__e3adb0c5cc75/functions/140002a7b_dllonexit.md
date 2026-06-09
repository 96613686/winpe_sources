# __dllonexit

- ea: `0x140002a7b`
- end: `0x140002a81`
- name: `__dllonexit`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002684`

## import_xrefs

- `msvcrt!__dllonexit` at `0x140002a7b`

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
0x140002a7b  jmp     cs:__imp___dllonexit
```
