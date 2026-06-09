# MergeSdbpLaunchProcess(ushort const *,ulong &)

- ea: `0x1800310a8`
- end: `0x1800312bb`
- name: `?MergeSdbpLaunchProcess@@YAKPEBGAEAK@Z`
- size: `531`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180030ff8`
- `0x180043424`

## callees

- `0x180012920`
- `0x1800310a8`
- `0x1800312d0`
- `0x1800312ec`
- `0x18004aa5c`
- `0x18004d110`
- `0x18004f378`
- `0x18007a9cf`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031205`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003121b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003121b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800311ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800311ac`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180031211`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180031211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003125b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003126f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003125b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003126f`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003113e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003114d`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003115c`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003113e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003114d`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18003115c`

## string_xrefs

- `0x1800311d1`: `CreateProcessW failed to create process for '%S' (%d)`

## pseudocode

```c

```
