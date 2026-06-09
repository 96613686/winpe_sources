# __p__commode

- ea: `0x14005bba8`
- end: `0x14005bbae`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14005a610`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__p__commode` at `0x14005bba8`

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
0x14005bba8  jmp     cs:__imp___p__commode
```
