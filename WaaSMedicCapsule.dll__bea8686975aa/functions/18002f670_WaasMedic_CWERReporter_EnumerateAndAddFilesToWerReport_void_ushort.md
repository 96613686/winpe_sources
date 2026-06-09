# WaasMedic::CWERReporter::EnumerateAndAddFilesToWerReport(void *,ushort *)

- ea: `0x18002f670`
- end: `0x18002f83c`
- name: `?EnumerateAndAddFilesToWerReport@CWERReporter@WaasMedic@@AEAAJPEAXPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(WaasMedic::CWERReporter *__hidden this, void *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002ed2c`
- `0x18002ede4`
- `0x18002f670`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x18000a5d0`
- `0x18002543c`
- `0x18002f670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f715`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f72f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f715`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f72f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002f80e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002f80e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002f7b9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002f7b9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002f700`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002f700`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x18002f7a7`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x18002f7a7`

## string_xrefs

- `0x18002f6db`: `Failed to create enumeration search filter for %s! hr = 0x%08x`
- `0x18002f78a`: `Failed to enumerate and add files to WER report for directory %s! hr = 0x%08x`

## pseudocode

```c

```
