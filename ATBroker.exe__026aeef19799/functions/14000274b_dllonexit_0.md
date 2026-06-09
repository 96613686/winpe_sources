# __dllonexit_0

- ea: `0x14000274b`
- end: `0x140002751`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002348`

## import_xrefs

- `msvcrt!__dllonexit` at `0x14000274b`

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
0x14000274b  jmp     cs:__imp___dllonexit
```
