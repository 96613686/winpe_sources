# _o___std_type_info_destroy_list

- ea: `0x180001d6e`
- end: `0x180001d74`
- name: `_o___std_type_info_destroy_list`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_type_info_destroy_list` at `0x180001d6e`

## pseudocode

```c
// attributes: thunk
__int64 o___std_type_info_destroy_list()
{
  return _o___std_type_info_destroy_list();
}

```

## disassembly

```asm
0x180001d6e  jmp     cs:__imp__o___std_type_info_destroy_list
```
