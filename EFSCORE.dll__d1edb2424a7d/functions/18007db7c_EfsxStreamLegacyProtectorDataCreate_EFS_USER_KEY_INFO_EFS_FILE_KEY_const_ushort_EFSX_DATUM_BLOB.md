# EfsxStreamLegacyProtectorDataCreate(_EFS_USER_KEY_INFO *,_EFS_FILE_KEY const *,ushort *,_EFSX_DATUM_BLOB * *)

- ea: `0x18007db7c`
- end: `0x18007de61`
- name: `?EfsxStreamLegacyProtectorDataCreate@@YAKPEAU_EFS_USER_KEY_INFO@@PEBU_EFS_FILE_KEY@@PEAGPEAPEAU_EFSX_DATUM_BLOB@@@Z`
- size: `741`
- prototype: `unsigned int __fastcall(struct _EFS_USER_KEY_INFO *, const struct _EFS_FILE_KEY *, unsigned __int16 *, struct _EFSX_DATUM_BLOB **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18007de68`

## callees

- `0x180005045`
- `0x180010bf0`
- `0x180063698`
- `0x180069810`
- `0x18006a3d4`
- `0x18007845c`
- `0x18007db7c`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd84`
- `bcrypt!BCryptExportKey` at `0x18007dbe7`
- `bcrypt!BCryptExportKey` at `0x18007dd28`
- `bcrypt!BCryptExportKey` at `0x18007dbe7`
- `bcrypt!BCryptExportKey` at `0x18007dd28`
- `ntdll!RtlNtStatusToDosError` at `0x18007dbf3`
- `ntdll!RtlNtStatusToDosError` at `0x18007dd37`
- `ntdll!RtlNtStatusToDosError` at `0x18007dbf3`
- `ntdll!RtlNtStatusToDosError` at `0x18007dd37`

## pseudocode

```c

```
