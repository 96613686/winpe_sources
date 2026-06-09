# __imp_load_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z

- ea: `0x18000262c`
- end: `0x180002638`
- name: `__imp_load_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x18000262c`

## pseudocode

```c
__int64 load__UpdateSheets_DUIXmlParser_DirectUI__QEAAJPEAVElement_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000262c  lea     rax, __imp_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z; DirectUI::DUIXmlParser::UpdateSheets(DirectUI::Element *)
0x180002633  jmp     __tailMerge_dui70_dll
```
