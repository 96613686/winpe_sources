# __std_type_info_destroy_list_0

- ea: `0x180001ea6`
- end: `0x180001eac`
- name: `__std_type_info_destroy_list_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000161c`

## import_xrefs

- `VCRUNTIME140_CLR0400!__std_type_info_destroy_list` at `0x180001ea6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _std_type_info_destroy_list_0(__int64 a1)
{
  return __std_type_info_destroy_list(a1);
}

```

## disassembly

```asm
0x180001ea6  jmp     cs:__imp___std_type_info_destroy_list
```
