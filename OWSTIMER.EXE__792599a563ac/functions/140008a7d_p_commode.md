# __p__commode

- ea: `0x140008a7d`
- end: `0x140008a83`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007de0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__p__commode` at `0x140008a7d`

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
0x140008a7d  jmp     cs:__imp___p__commode
```
