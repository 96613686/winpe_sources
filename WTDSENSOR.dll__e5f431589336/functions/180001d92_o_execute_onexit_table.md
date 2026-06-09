# _o__execute_onexit_table

- ea: `0x180001d92`
- end: `0x180001d98`
- name: `_o__execute_onexit_table`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__execute_onexit_table` at `0x180001d92`

## pseudocode

```c
// attributes: thunk
__int64 o__execute_onexit_table()
{
  return _o__execute_onexit_table();
}

```

## disassembly

```asm
0x180001d92  jmp     cs:__imp__o__execute_onexit_table
```
