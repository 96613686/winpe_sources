# __std_type_info_destroy_list

- ea: `0x180001bfe`
- end: `0x180001c04`
- name: `__std_type_info_destroy_list`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_type_info_destroy_list` at `0x180001bfe`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _std_type_info_destroy_list(__int64 a1)
{
  return __std_type_info_destroy_list(a1);
}

```

## disassembly

```asm
0x180001bfe  jmp     cs:__imp___std_type_info_destroy_list
```
