# _execute_onexit_table

- ea: `0x180001c42`
- end: `0x180001c48`
- name: `_execute_onexit_table`
- size: `6`
- prototype: `int __cdecl(_onexit_table_t *Table)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__execute_onexit_table` at `0x180001c42`

## pseudocode

```c
// attributes: thunk
int __cdecl execute_onexit_table(_onexit_table_t *Table)
{
  return _execute_onexit_table(Table);
}

```

## disassembly

```asm
0x180001c42  jmp     cs:__imp__execute_onexit_table
```
