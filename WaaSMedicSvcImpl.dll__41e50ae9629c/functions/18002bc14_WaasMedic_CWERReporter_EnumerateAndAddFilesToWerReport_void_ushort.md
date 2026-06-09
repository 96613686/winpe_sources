# WaasMedic::CWERReporter::EnumerateAndAddFilesToWerReport(void *,ushort *)

- ea: `0x18002bc14`
- end: `0x18002bde0`
- name: `?EnumerateAndAddFilesToWerReport@CWERReporter@WaasMedic@@AEAAJPEAXPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(WaasMedic::CWERReporter *__hidden this, void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002b63c`
- `0x18002bc14`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000c638`
- `0x18002bc14`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcb9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcb9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bcd3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002bd5d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002bd5d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002bdb2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002bdb2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002bca4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002bca4`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x18002bd4b`
- `ext-ms-win-wer-reporting-l1-1-0!WerReportAddFile` at `0x18002bd4b`

## string_xrefs

- `0x18002bc7f`: `Failed to create enumeration search filter for %s! hr = 0x%08x`
- `0x18002bd2e`: `Failed to enumerate and add files to WER report for directory %s! hr = 0x%08x`

## pseudocode

```c

```
