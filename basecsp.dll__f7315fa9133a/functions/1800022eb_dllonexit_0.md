# __dllonexit_0

- ea: `0x1800022eb`
- end: `0x1800022f1`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f64`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800022eb`

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
0x1800022eb  jmp     cs:__imp___dllonexit
```
