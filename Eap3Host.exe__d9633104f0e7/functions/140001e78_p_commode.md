# __p__commode

- ea: `0x140001e78`
- end: `0x140001e7e`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x140001e78`

## pseudocode

```c
// attributes: thunk
int *__cdecl _p__commode()
{
  return __p__commode();
}

```

## disassembly

```asm
0x140001e78  jmp     cs:__imp___p__commode
```
