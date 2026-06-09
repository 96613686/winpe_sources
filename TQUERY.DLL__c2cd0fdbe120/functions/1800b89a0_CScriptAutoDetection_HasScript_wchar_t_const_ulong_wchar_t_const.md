# CScriptAutoDetection::HasScript(wchar_t const *,ulong,wchar_t const *)

- ea: `0x1800b89a0`
- end: `0x1800b8c23`
- name: `?HasScript@CScriptAutoDetection@@QEAAJPEB_WK0@Z`
- size: `643`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180056a80`

## callees

- `0x1800b89a0`
- `0x180189cce`
- `0x18018a0e1`
- `0x18018a123`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8b9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b8b9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b8bf5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800b8b73`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800b8b73`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800b89f4`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800b89f4`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800b8b33`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800b8b33`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800b8bd2`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800b8bd2`

## pseudocode

```c

```
