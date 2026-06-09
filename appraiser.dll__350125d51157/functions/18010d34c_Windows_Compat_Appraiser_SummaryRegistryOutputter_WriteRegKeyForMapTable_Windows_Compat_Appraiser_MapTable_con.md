# Windows::Compat::Appraiser::SummaryRegistryOutputter::WriteRegKeyForMapTable(Windows::Compat::Appraiser::MapTable const *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::IPropertyListEnumerator *,Windows::Compat::Appraiser::TableCache *)

- ea: `0x18010d34c`
- end: `0x18010da99`
- name: `?WriteRegKeyForMapTable@SummaryRegistryOutputter@Appraiser@Compat@Windows@@AEAAJPEBUMapTable@234@PEAVIPropertyListEnumerator@234@1111PEAVTableCache@234@@Z`
- size: `1869`
- prototype: `int(Windows::Compat::Appraiser::SummaryRegistryOutputter *__hidden this, const struct Windows::Compat::Appraiser::MapTable *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *, struct Windows::Compat::Appraiser::TableCache *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010c130`

## callees

- `0x18000147c`
- `0x180003148`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x18002750c`
- `0x1800291c8`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180048724`
- `0x1800b1734`
- `0x18010c64c`
- `0x18010c9bc`
- `0x18010d34c`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18010d571`
- `KERNEL32!GetSystemTime` at `0x18010d95d`
- `KERNEL32!GetSystemTime` at `0x18010d571`
- `KERNEL32!GetSystemTime` at `0x18010d95d`
- `KERNEL32!GetProcessHeap` at `0x18010d9d7`
- `KERNEL32!GetProcessHeap` at `0x18010d9f4`
- `KERNEL32!GetProcessHeap` at `0x18010da11`
- `KERNEL32!GetProcessHeap` at `0x18010d9d7`
- `KERNEL32!GetProcessHeap` at `0x18010d9f4`
- `KERNEL32!GetProcessHeap` at `0x18010da11`
- `KERNEL32!HeapFree` at `0x18010d9e5`
- `KERNEL32!HeapFree` at `0x18010da02`
- `KERNEL32!HeapFree` at `0x18010da1f`
- `KERNEL32!HeapFree` at `0x18010d9e5`
- `KERNEL32!HeapFree` at `0x18010da02`
- `KERNEL32!HeapFree` at `0x18010da1f`

## string_xrefs

- `0x18010d3f9`: `onecore\base\appcompat\appraiser\outputters\summaryregistry.cpp`
- `0x18010d430`: `onecore\base\appcompat\appraiser\outputters\summaryregistry.cpp`
- `0x18010d495`: `Error reading old reg value: [0x%x].`
- `0x18010d5e9`: `Error reading old reg value: [0x%x].`
- `0x18010d400`: `Windows::Compat::Appraiser::SummaryRegistryOutputter::WriteRegKeyForMapTable`
- `0x18010d424`: `Windows::Compat::Appraiser::SummaryRegistryOutputter::WriteRegKeyForMapTable`

## pseudocode

```c

```
