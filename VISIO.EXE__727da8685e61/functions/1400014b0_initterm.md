# _initterm

- ea: `0x1400014b0`
- end: `0x1400014b6`
- name: `_initterm`
- size: `6`
- prototype: `void __cdecl(_PVFV *First, _PVFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001570`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm` at `0x1400014b0`

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
0x1400014b0  jmp     cs:__imp__initterm
```
