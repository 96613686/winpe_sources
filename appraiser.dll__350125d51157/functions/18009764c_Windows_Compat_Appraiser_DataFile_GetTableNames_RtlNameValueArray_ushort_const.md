# Windows::Compat::Appraiser::DataFile::GetTableNames(RtlNameValueArray &,ushort const *)

- ea: `0x18009764c`
- end: `0x180097da1`
- name: `?GetTableNames@DataFile@Appraiser@Compat@Windows@@CAJAEAVRtlNameValueArray@@PEBG@Z`
- size: `1877`
- prototype: `__int64 __fastcall(struct RtlNameValueArray *this, char *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180097108`
- `0x180098090`

## callees

- `0x180008570`
- `0x180013f90`
- `0x1800144c4`
- `0x18001a558`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800390b0`
- `0x180088d48`
- `0x18008f84c`
- `0x180096e14`
- `0x180096f80`
- `0x18009764c`
- `0x180098424`
- `0x18009b0a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800978b8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800978b8`
- `KERNEL32!GetPrivateProfileStringW` at `0x180097784`
- `KERNEL32!GetPrivateProfileStringW` at `0x180097784`
- `KERNEL32!GetProcessHeap` at `0x180097695`
- `KERNEL32!GetProcessHeap` at `0x1800976f3`
- `KERNEL32!GetProcessHeap` at `0x180097737`
- `KERNEL32!GetProcessHeap` at `0x180097751`
- `KERNEL32!GetProcessHeap` at `0x180097d28`
- `KERNEL32!GetProcessHeap` at `0x180097695`
- `KERNEL32!GetProcessHeap` at `0x1800976f3`
- `KERNEL32!GetProcessHeap` at `0x180097737`
- `KERNEL32!GetProcessHeap` at `0x180097751`
- `KERNEL32!GetProcessHeap` at `0x180097d28`
- `KERNEL32!HeapAlloc` at `0x18009775f`
- `KERNEL32!HeapAlloc` at `0x18009775f`
- `KERNEL32!HeapFree` at `0x180097745`
- `KERNEL32!HeapFree` at `0x180097d36`
- `KERNEL32!HeapFree` at `0x180097d53`
- `KERNEL32!HeapFree` at `0x180097d72`
- `KERNEL32!HeapFree` at `0x180097745`
- `KERNEL32!HeapFree` at `0x180097d36`
- `KERNEL32!HeapFree` at `0x180097d53`
- `KERNEL32!HeapFree` at `0x180097d72`

## string_xrefs

- `0x1800977dc`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180097d13`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180097cfb`: `Failed to read decision tables from %ls.`
- `0x1800977d5`: `Windows::Compat::Appraiser::DataFile::GetTableNames`
- `0x180097d0c`: `Windows::Compat::Appraiser::DataFile::GetTableNames`
- `0x1800979ec`: `Failed to remove table from set of available tables: [0x%x].`
- `0x180097abe`: `Failed to remove table from set of available tables: [0x%x].`
- `0x180097bf2`: `Cannot have competing data file tables that specify the exact same min version.`
- `0x180097c00`: `Cannot have competing data file tables that specify different types of min version restrictions.`

## pseudocode

```c

```
