# __imp_load_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z

- ea: `0x180002662`
- end: `0x18000266e`
- name: `__imp_load_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x180002662`

## pseudocode

```c
__int64 load__Create_FillLayout_DirectUI__SAJPEAPEAVLayout_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002662  lea     rax, __imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x180002669  jmp     __tailMerge_dui70_dll
```
