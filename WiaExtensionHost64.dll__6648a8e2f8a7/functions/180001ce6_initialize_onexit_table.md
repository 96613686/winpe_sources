# _initialize_onexit_table

- ea: `0x180001ce6`
- end: `0x180001cec`
- name: `_initialize_onexit_table`
- size: `6`
- prototype: `int __cdecl(_onexit_table_t *Table)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__initialize_onexit_table` at `0x180001ce6`

## pseudocode

```c
// attributes: thunk
int __cdecl initialize_onexit_table(_onexit_table_t *Table)
{
  return _o__initialize_onexit_table(Table);
}

```

## disassembly

```asm
0x180001ce6  jmp     cs:__imp__o__initialize_onexit_table
```
