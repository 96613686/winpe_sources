# __dllonexit

- ea: `0x14000ac7e`
- end: `0x14000ac84`
- name: `__dllonexit`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000a698`

## import_xrefs

- `msvcrt!__dllonexit` at `0x14000ac7e`

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
0x14000ac7e  jmp     cs:__imp___dllonexit
```
