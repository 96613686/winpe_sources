# CInpagePlugIn::GetFaultingIOFilePath(void *,wchar_t *,ulong)

- ea: `0x1400476bc`
- end: `0x140047826`
- name: `?GetFaultingIOFilePath@CInpagePlugIn@@AEAAJPEAXPEA_WK@Z`
- size: `362`
- prototype: `int(CInpagePlugIn *__hidden this, void *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140047b20`

## callees

- `0x140002470`
- `0x140011f24`
- `0x14001444c`
- `0x1400476bc`
- `0x14004782c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004772d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400477dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004772d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400477dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047791`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400477b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400477b7`

## string_xrefs

- `0x140047703`: `psapi.dll`

## pseudocode

```c

```
