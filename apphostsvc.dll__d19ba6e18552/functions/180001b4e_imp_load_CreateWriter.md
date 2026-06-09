# __imp_load_CreateWriter

- ea: `0x180001b4e`
- end: `0x180001b5a`
- name: `__imp_load_CreateWriter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001acf`

## import_xrefs

- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x180001b4e`

## pseudocode

```c
__int64 load_CreateWriter()
{
  return _tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001b4e  lea     rax, __imp_CreateWriter
0x180001b55  jmp     __tailMerge_ext_ms_win_fs_vssapi_l1_1_0_dll
```
