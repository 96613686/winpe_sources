# StateRepository::Logging::_WriteLogToFile(char const *)

- ea: `0x180075bdc`
- end: `0x180075d48`
- name: `?_WriteLogToFile@Logging@StateRepository@@YAJPEBD@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18012a0ec`

## callees

- `0x180005020`
- `0x18003bea4`
- `0x180075bdc`
- `0x1800762a8`
- `0x1800aed10`
- `0x1800da6cc`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180075c86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180075c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075cfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075cbd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075cbd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180075cea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180075cea`

## string_xrefs

- `0x180075c5d`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c

```
