# GetStandardInfo(bool,wil::basic_zstring_view<wchar_t> const &,_FILE_STANDARD_INFO *)

- ea: `0x18002de00`
- end: `0x18002dfd8`
- name: `?GetStandardInfo@@YAJ_NAEBV?$basic_zstring_view@_W@wil@@PEAU_FILE_STANDARD_INFO@@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002d5ac`

## callees

- `0x1800031d0`
- `0x180009750`
- `0x18000ba14`
- `0x18002bf3c`
- `0x18002cdf8`
- `0x18002de00`

## import_xrefs

- `ntdll!NtClose` at `0x18002def1`
- `ntdll!NtClose` at `0x18002df71`
- `ntdll!NtClose` at `0x18002dfa1`
- `ntdll!NtClose` at `0x18002def1`
- `ntdll!NtClose` at `0x18002df71`
- `ntdll!NtClose` at `0x18002dfa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de91`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002df20`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002df20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002de73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002de73`

## string_xrefs

- `0x18002df48`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c

```
