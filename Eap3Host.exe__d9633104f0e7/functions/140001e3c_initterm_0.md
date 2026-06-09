# _initterm_0

- ea: `0x140001e3c`
- end: `0x140001e42`
- name: `_initterm_0`
- size: `6`
- prototype: `void __cdecl(_PVFV *First, _PVFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm` at `0x140001e3c`

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
0x140001e3c  jmp     cs:__imp__initterm
```
