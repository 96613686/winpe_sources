# __p__commode

- ea: `0x140001e1e`
- end: `0x140001e24`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x140001e1e`

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
0x140001e1e  jmp     cs:__imp___p__commode
```
