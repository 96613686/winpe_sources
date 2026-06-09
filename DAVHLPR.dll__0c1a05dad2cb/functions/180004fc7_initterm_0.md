# _initterm_0

- ea: `0x180004fc7`
- end: `0x180004fcd`
- name: `_initterm_0`
- size: `6`
- prototype: `void __cdecl(_PVFV *First, _PVFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180004970`

## import_xrefs

- `msvcrt!_initterm` at `0x180004fc7`

## pseudocode

```c
// attributes: thunk
void __cdecl initterm_0(_PVFV *First, _PVFV *Last)
{
  _initterm(First, Last);
}

```

## disassembly

```asm
0x180004fc7  jmp     cs:__imp__initterm
```
