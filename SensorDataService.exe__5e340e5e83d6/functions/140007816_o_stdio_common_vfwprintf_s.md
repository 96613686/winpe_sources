# _o___stdio_common_vfwprintf_s

- ea: `0x140007816`
- end: `0x14000781c`
- name: `_o___stdio_common_vfwprintf_s`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfwprintf_s` at `0x140007816`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vfwprintf_s()
{
  return _o___stdio_common_vfwprintf_s();
}

```

## disassembly

```asm
0x140007816  jmp     cs:__imp__o___stdio_common_vfwprintf_s
```
