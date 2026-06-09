# _o___p__commode

- ea: `0x1400077f2`
- end: `0x1400077f8`
- name: `_o___p__commode`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140006cb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x1400077f2`

## pseudocode

```c
// attributes: thunk
__int64 o___p__commode()
{
  return _o___p__commode();
}

```

## disassembly

```asm
0x1400077f2  jmp     cs:__imp__o___p__commode
```
