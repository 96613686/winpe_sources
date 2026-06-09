# CloudServiceDateTime::IsoTimeToFileTime(ushort const *,_FILETIME *)

- ea: `0x18008ede8`
- end: `0x18008efe7`
- name: `?IsoTimeToFileTime@CloudServiceDateTime@@SAJPEBGPEAU_FILETIME@@@Z`
- size: `511`
- prototype: `static int(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800795d0`
- `0x1800948d0`

## callees

- `0x180008870`
- `0x180008898`
- `0x18000a754`
- `0x18000b7d4`
- `0x18000bf7c`
- `0x18008eb3c`
- `0x18008ede8`
- `0x18008eff0`
- `0x18008f260`
- `0x18008f290`
- `0x1800c6940`

## import_xrefs

- `msvcrt!_wtoi` at `0x18008eeb5`
- `msvcrt!_wtoi` at `0x18008eeb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef6d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008ef63`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008ef63`

## pseudocode

```c

```
