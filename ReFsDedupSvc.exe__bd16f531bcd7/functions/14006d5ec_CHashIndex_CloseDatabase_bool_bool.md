# CHashIndex::CloseDatabase(bool,bool)

- ea: `0x14006d5ec`
- end: `0x14006d6df`
- name: `?CloseDatabase@CHashIndex@@AEAAX_N0@Z`
- size: `243`
- prototype: `void __fastcall(CHashIndex *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x14006e690`
- `0x14007262c`

## callees

- `0x140019600`
- `0x140063a2c`
- `0x140063dd8`
- `0x14006d5ec`
- `0x1401b9010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x14006d62f`
- `ntdll!NtSetInformationFile` at `0x14006d62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d6bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006d6bd`

## string_xrefs

- `0x14006d667`: `Unable to delete DB after optimization, path = %s, error = 0x%x\n`
- `0x14006d68d`: `[DBG] DB file %s deleted.\n`

## pseudocode

```c

```
