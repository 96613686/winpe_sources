# __imp_load_DeleteDC

- ea: `0x180005698`
- end: `0x1800056a4`
- name: `__imp_load_DeleteDC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005619`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180005698`

## pseudocode

```c
__int64 load_DeleteDC()
{
  return _tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll();
}

```

## disassembly

```asm
0x180005698  lea     rax, __imp_DeleteDC
0x18000569f  jmp     __tailMerge_ext_ms_win_gdi_dc_create_l1_1_0_dll
```
