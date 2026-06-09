# _initterm_e

- ea: `0x180001d62`
- end: `0x180001d68`
- name: `_initterm_e`
- size: `6`
- prototype: `int __cdecl(_PIFV *First, _PIFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm_e` at `0x180001d62`

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
0x180001d62  jmp     cs:__imp__initterm_e
```
