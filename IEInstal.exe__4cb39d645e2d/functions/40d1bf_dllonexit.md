# ___dllonexit

- ea: `0x40d1bf`
- end: `0x40d1c5`
- name: `___dllonexit`
- size: `6`
- prototype: `int()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x40ccf0`

## import_xrefs

- `msvcrt!__dllonexit` at `0x40d1bf`

## pseudocode

```c
// attributes: thunk
int __dllonexit()
{
  return ___dllonexit();
}

```

## disassembly

```asm
0x40d1bf  jmp     ds:__imp____dllonexit
```
