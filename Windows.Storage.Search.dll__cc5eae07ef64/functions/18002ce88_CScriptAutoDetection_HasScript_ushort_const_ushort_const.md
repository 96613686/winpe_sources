# CScriptAutoDetection::HasScript(ushort const *,ushort const *)

- ea: `0x18002ce88`
- end: `0x18002cfe7`
- name: `?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z`
- size: `351`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002c2c0`

## callees

- `0x18002ce88`
- `0x180072cf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cf92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cf92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cf79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cf79`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002cf33`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002cf33`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18002cf58`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x18002cf58`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18002cfc8`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18002cfc8`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18002cf00`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x18002cf00`

## pseudocode

```c

```
