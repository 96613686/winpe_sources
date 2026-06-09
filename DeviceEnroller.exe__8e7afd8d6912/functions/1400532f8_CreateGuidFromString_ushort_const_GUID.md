# CreateGuidFromString(ushort const *,_GUID *)

- ea: `0x1400532f8`
- end: `0x140053427`
- name: `?CreateGuidFromString@@YAJPEBGPEAU_GUID@@@Z`
- size: `303`
- prototype: `signed int __fastcall(RPC_WSTR StringUuid, struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140054320`
- `0x140055960`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x1400532f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400533ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400533ba`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400533b0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400533b0`
- `RPCRT4!UuidFromStringW` at `0x1400533d6`
- `RPCRT4!UuidFromStringW` at `0x1400533d6`

## pseudocode

```c

```
