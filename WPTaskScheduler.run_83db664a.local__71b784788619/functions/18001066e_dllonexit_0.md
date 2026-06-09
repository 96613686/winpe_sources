# __dllonexit_0

- ea: `0x18001066e`
- end: `0x180010674`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800100bc`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18001066e`

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
0x18001066e  jmp     cs:__imp___dllonexit
```
