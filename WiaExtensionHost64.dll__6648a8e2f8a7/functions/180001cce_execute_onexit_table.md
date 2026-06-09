# _execute_onexit_table

- ea: `0x180001cce`
- end: `0x180001cd4`
- name: `_execute_onexit_table`
- size: `6`
- prototype: `int __cdecl(_onexit_table_t *Table)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__execute_onexit_table` at `0x180001cce`

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
0x180001cce  jmp     cs:__imp__execute_onexit_table
```
