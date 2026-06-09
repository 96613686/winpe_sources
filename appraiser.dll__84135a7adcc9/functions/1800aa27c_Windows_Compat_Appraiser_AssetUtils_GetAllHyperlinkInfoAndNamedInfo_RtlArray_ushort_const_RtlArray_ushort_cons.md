# Windows::Compat::Appraiser::AssetUtils::GetAllHyperlinkInfoAndNamedInfo(RtlArray<ushort const *> &,RtlArray<ushort const *> &,RtlArray<ushort const *> &,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::MapTable *,Windows::Compat::Appraiser::MapTable *)

- ea: `0x1800aa27c`
- end: `0x1800aaca3`
- name: `?GetAllHyperlinkInfoAndNamedInfo@AssetUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@00PEAVIAsset@234@PEAUMapTable@234@2@Z`
- size: `2599`
- prototype: `__int64 __fastcall(int, int, int, int, struct Windows::Compat::Appraiser::MapTable *, struct Windows::Compat::Appraiser::MapTable *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1801117ec`

## callees

- `0x1800092dc`
- `0x18000a594`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003b2a0`
- `0x18009606c`
- `0x1800aa27c`
- `0x1800ae950`
- `0x1800b34a0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800aa2c6`
- `KERNEL32!GetProcessHeap` at `0x1800aa304`
- `KERNEL32!GetProcessHeap` at `0x1800aa32e`
- `KERNEL32!GetProcessHeap` at `0x1800aa358`
- `KERNEL32!GetProcessHeap` at `0x1800aa48f`
- `KERNEL32!GetProcessHeap` at `0x1800aa2c6`
- `KERNEL32!GetProcessHeap` at `0x1800aa304`
- `KERNEL32!GetProcessHeap` at `0x1800aa32e`
- `KERNEL32!GetProcessHeap` at `0x1800aa358`
- `KERNEL32!GetProcessHeap` at `0x1800aa48f`
- `KERNEL32!HeapFree` at `0x1800aac13`
- `KERNEL32!HeapFree` at `0x1800aac37`
- `KERNEL32!HeapFree` at `0x1800aac5b`
- `KERNEL32!HeapFree` at `0x1800aac80`
- `KERNEL32!HeapFree` at `0x1800aac13`
- `KERNEL32!HeapFree` at `0x1800aac37`
- `KERNEL32!HeapFree` at `0x1800aac5b`
- `KERNEL32!HeapFree` at `0x1800aac80`

## string_xrefs

- `0x1800aa3ad`: `onecore\base\appcompat\appraiser\helpers\assetutils.cpp`
- `0x1800aa3de`: `onecore\base\appcompat\appraiser\helpers\assetutils.cpp`
- `0x1800aa888`: `SdbHyperlinkTarget`
- `0x1800aa9f7`: `SdbHyperlinkText`
- `0x1800aa610`: `Failed to retrieve Hyperlink Info from MapTable`
- `0x1800aa643`: `Failed to retrieve Hyperlink Info from MapTable`
- `0x1800aa3a6`: `Windows::Compat::Appraiser::AssetUtils::GetAllHyperlinkInfoAndNamedInfo`
- `0x1800aa3d7`: `Windows::Compat::Appraiser::AssetUtils::GetAllHyperlinkInfoAndNamedInfo`

## pseudocode

```c

```
