# EfsxStreamProtectorDataCreate(_EFS_USER_KEY_INFO *,_EFS_FILE_KEY const *,ushort *,_EFSX_DATUM_KEY_AGMT_DATA * *)

- ea: `0x18007e194`
- end: `0x18007e4f8`
- name: `?EfsxStreamProtectorDataCreate@@YAKPEAU_EFS_USER_KEY_INFO@@PEBU_EFS_FILE_KEY@@PEAGPEAPEAU_EFSX_DATUM_KEY_AGMT_DATA@@@Z`
- size: `868`
- prototype: `unsigned int __fastcall(struct _EFS_USER_KEY_INFO *, const struct _EFS_FILE_KEY *, unsigned __int16 *, struct _EFSX_DATUM_KEY_AGMT_DATA **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18007de68`

## callees

- `0x180025e68`
- `0x18004a89c`
- `0x180063698`
- `0x180069810`
- `0x18006a3d4`
- `0x18006ac64`
- `0x18007e194`
- `0x180080224`
- `0x1800d87ac`
- `0x1800dca3c`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18007e27e`
- `bcrypt!BCryptExportKey` at `0x18007e382`
- `bcrypt!BCryptExportKey` at `0x18007e27e`
- `bcrypt!BCryptExportKey` at `0x18007e382`
- `bcrypt!BCryptDestroyKey` at `0x18007e4c0`
- `bcrypt!BCryptDestroyKey` at `0x18007e4c0`
- `ntdll!RtlNtStatusToDosError` at `0x18007e28a`
- `ntdll!RtlNtStatusToDosError` at `0x18007e38e`
- `ntdll!RtlNtStatusToDosError` at `0x18007e28a`
- `ntdll!RtlNtStatusToDosError` at `0x18007e38e`

## pseudocode

```c

```
