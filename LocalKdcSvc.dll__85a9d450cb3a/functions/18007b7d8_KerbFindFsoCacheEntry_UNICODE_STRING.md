# KerbFindFsoCacheEntry(_UNICODE_STRING *)

- ea: `0x18007b7d8`
- end: `0x18007b85f`
- name: `?KerbFindFsoCacheEntry@@YAPEAU_KERB_FSO_CACHE_ENTRY@@PEAU_UNICODE_STRING@@@Z`
- size: `135`
- prototype: `struct _KERB_FSO_CACHE_ENTRY *__fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007a5cc`

## callees

- `0x18007b7d8`
- `0x18007bad0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18007b81e`
- `ntdll!RtlEqualUnicodeString` at `0x18007b81e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007b841`
- `ntdll!RtlLeaveCriticalSection` at `0x18007b841`
- `ntdll!RtlEnterCriticalSection` at `0x18007b7f3`
- `ntdll!RtlEnterCriticalSection` at `0x18007b7f3`

## pseudocode

```c

```
