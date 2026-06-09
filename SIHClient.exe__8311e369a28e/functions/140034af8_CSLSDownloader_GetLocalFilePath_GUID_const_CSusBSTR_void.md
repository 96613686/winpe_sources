# CSLSDownloader::GetLocalFilePath(_GUID const &,CSusBSTR &,void *)

- ea: `0x140034af8`
- end: `0x140034cc3`
- name: `?GetLocalFilePath@CSLSDownloader@@AEAAJAEBU_GUID@@AEAVCSusBSTR@@PEAX@Z`
- size: `459`
- prototype: `__int64 __fastcall(CSLSDownloader *this, const struct _GUID *, BSTR *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003401c`

## callees

- `0x14000e194`
- `0x14000ee68`
- `0x1400154b4`
- `0x1400326d0`
- `0x140034af8`
- `0x140045dc0`
- `0x14004621c`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140034bd4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140034bd4`
- `OLEAUT32!__imp_SysFreeString` at `0x140034b90`
- `OLEAUT32!__imp_SysFreeString` at `0x140034b90`

## string_xrefs

- `0x140034c77`: `SusMakeDirectoryForFile`

## pseudocode

```c

```
