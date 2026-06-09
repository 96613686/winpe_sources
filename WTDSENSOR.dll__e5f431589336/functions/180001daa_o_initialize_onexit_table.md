# _o__initialize_onexit_table

- ea: `0x180001daa`
- end: `0x180001db0`
- name: `_o__initialize_onexit_table`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001838`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__initialize_onexit_table` at `0x180001daa`

## pseudocode

```c
// attributes: thunk
__int64 o__initialize_onexit_table()
{
  return _o__initialize_onexit_table();
}

```

## disassembly

```asm
0x180001daa  jmp     cs:__imp__o__initialize_onexit_table
```
