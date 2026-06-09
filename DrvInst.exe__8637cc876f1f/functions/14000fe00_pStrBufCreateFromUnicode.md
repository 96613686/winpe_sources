# pStrBufCreateFromUnicode

- ea: `0x14000fe00`
- end: `0x14000fe98`
- name: `pStrBufCreateFromUnicode`
- size: `152`
- prototype: `__int64 __fastcall(PCWCH UnicodeString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fac4`

## callees

- `0x14000fa4c`
- `0x14000fd90`
- `0x14000fe00`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteN` at `0x14000fe76`
- `ntdll!RtlUnicodeToMultiByteN` at `0x14000fe76`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x14000fe2d`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x14000fe2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fe3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fe3c`

## pseudocode

```c

```
