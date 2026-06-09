# _initterm_e

- ea: `0x1400014c0`
- end: `0x1400014c6`
- name: `_initterm_e`
- size: `6`
- prototype: `int __cdecl(_PIFV *First, _PIFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001570`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm_e` at `0x1400014c0`

## pseudocode

```c
// attributes: thunk
int __cdecl initterm_e(_PIFV *First, _PIFV *Last)
{
  return _initterm_e(First, Last);
}

```

## disassembly

```asm
0x1400014c0  jmp     cs:__imp__initterm_e
```
