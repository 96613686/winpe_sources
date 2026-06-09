# _initterm

- ea: `0x180001d56`
- end: `0x180001d5c`
- name: `_initterm`
- size: `6`
- prototype: `void __cdecl(_PVFV *First, _PVFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm` at `0x180001d56`

## pseudocode

```c
// attributes: thunk
void __cdecl initterm(_PVFV *First, _PVFV *Last)
{
  _initterm(First, Last);
}

```

## disassembly

```asm
0x180001d56  jmp     cs:__imp__initterm
```
