# s_SendWERForReentrancy(void *)

- ea: `0x1801e5e40`
- end: `0x1801e61a2`
- name: `?s_SendWERForReentrancy@@YAKPEAX@Z`
- size: `866`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800243b0`
- `0x180047410`
- `0x1800688b0`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801e5e40`
- `0x180206010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801e6061`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801e6061`
- `SHLWAPI!PathFindFileNameW` at `0x1801e5f2b`
- `SHLWAPI!PathFindFileNameW` at `0x1801e5f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801e5ec7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801e5ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801e60f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801e60f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e602c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e602c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801e5f85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801e5f85`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1801e5f6e`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1801e5f6e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1801e5fe0`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1801e5fe0`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1801e5fad`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1801e5fad`
- `wer!WerReportSetParameter` at `0x1801e60a2`
- `wer!WerReportSetParameter` at `0x1801e60c6`
- `wer!WerReportSetParameter` at `0x1801e60ea`
- `wer!WerReportSetParameter` at `0x1801e60a2`
- `wer!WerReportSetParameter` at `0x1801e60c6`
- `wer!WerReportSetParameter` at `0x1801e60ea`
- `wer!WerReportCreate` at `0x1801e6083`
- `wer!WerReportCreate` at `0x1801e6083`
- `wer!WerReportAddDump` at `0x1801e6122`
- `wer!WerReportAddDump` at `0x1801e6122`
- `wer!WerReportCloseHandle` at `0x1801e6150`
- `wer!WerReportCloseHandle` at `0x1801e6150`
- `wer!WerReportSubmit` at `0x1801e6145`
- `wer!WerReportSubmit` at `0x1801e6145`

## pseudocode

```c

```
