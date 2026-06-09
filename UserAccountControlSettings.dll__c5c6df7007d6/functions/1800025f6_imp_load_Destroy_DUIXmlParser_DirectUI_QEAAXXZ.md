# __imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ

- ea: `0x1800025f6`
- end: `0x180002602`
- name: `__imp_load_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800025f6`

## pseudocode

```c
__int64 load__Destroy_DUIXmlParser_DirectUI__QEAAXXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x1800025f6  lea     rax, __imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800025fd  jmp     __tailMerge_dui70_dll
```
