# CScriptAutoDetection::HasScript(ushort const *,ushort const *)

- ea: `0x18005492c`
- end: `0x180054a8d`
- name: `?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z`
- size: `353`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180052b10`

## callees

- `0x18005492c`
- `0x180189cce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054a20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a73`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800549d7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800549d7`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800549fc`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800549fc`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800549a4`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800549a4`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180054a56`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180054a56`

## pseudocode

```c

```
