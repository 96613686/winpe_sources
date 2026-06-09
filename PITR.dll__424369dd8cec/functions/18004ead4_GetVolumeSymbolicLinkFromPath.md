# GetVolumeSymbolicLinkFromPath

- ea: `0x18004ead4`
- end: `0x18004edea`
- name: `GetVolumeSymbolicLinkFromPath`
- size: `790`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x18004dc58`

## callees

- `0x18004dbe8`
- `0x18004e358`
- `0x18004ead4`
- `0x180050300`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x18004ec75`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ecc4`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ed69`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ec75`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ecc4`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ed69`

## pseudocode

```c

```
