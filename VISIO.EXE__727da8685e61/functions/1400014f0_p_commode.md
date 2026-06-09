# __p__commode

- ea: `0x1400014f0`
- end: `0x1400014f6`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001750`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__p__commode` at `0x1400014f0`

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
0x1400014f0  jmp     cs:__imp___p__commode
```
