# __imp_load_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z

- ea: `0x180002566`
- end: `0x180002572`
- name: `__imp_load_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180002566`

## pseudocode

```c
__int64 load__Create_DUIXmlParser_DirectUI__SAJPEAPEAV12_P6APEAVValue_2_PEBGPEAX_Z2P6AX11H2_Z2_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002566  lea     rax, __imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18000256d  jmp     __tailMerge_dui70_dll
```
