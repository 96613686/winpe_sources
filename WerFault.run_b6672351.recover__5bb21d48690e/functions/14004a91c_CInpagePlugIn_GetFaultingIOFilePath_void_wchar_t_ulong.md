# CInpagePlugIn::GetFaultingIOFilePath(void *,wchar_t *,ulong)

- ea: `0x14004a91c`
- end: `0x14004aaa5`
- name: `?GetFaultingIOFilePath@CInpagePlugIn@@AEAAJPEAXPEA_WK@Z`
- size: `393`
- prototype: `int(CInpagePlugIn *__hidden this, void *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14004adc0`

## callees

- `0x140002490`
- `0x140012784`
- `0x140014ee4`
- `0x14004a91c`
- `0x14004aaac`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004a98d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004aa55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004a98d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004aa55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a9fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004a9fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004a99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa29`

## string_xrefs

- `0x14004a963`: `psapi.dll`

## pseudocode

```c

```
