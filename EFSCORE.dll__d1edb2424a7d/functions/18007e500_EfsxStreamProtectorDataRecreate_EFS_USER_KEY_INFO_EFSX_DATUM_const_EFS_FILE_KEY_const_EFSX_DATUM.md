# EfsxStreamProtectorDataRecreate(_EFS_USER_KEY_INFO *,_EFSX_DATUM const *,_EFS_FILE_KEY const *,_EFSX_DATUM * *)

- ea: `0x18007e500`
- end: `0x18007e955`
- name: `?EfsxStreamProtectorDataRecreate@@YAKPEAU_EFS_USER_KEY_INFO@@PEBU_EFSX_DATUM@@PEBU_EFS_FILE_KEY@@PEAPEAU2@@Z`
- size: `1109`
- prototype: `unsigned int(struct _EFS_USER_KEY_INFO *, const struct _EFSX_DATUM *, const struct _EFS_FILE_KEY *, struct _EFSX_DATUM **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18007eb90`

## callees

- `0x180025e68`
- `0x180026454`
- `0x18004a89c`
- `0x180063698`
- `0x180069810`
- `0x180069a20`
- `0x18006a3d4`
- `0x18006ac64`
- `0x18007e500`
- `0x18007f60c`
- `0x1800d87ac`
- `0x1800dca3c`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18007e6db`
- `bcrypt!BCryptExportKey` at `0x18007e804`
- `bcrypt!BCryptExportKey` at `0x18007e6db`
- `bcrypt!BCryptExportKey` at `0x18007e804`
- `bcrypt!BCryptDestroyKey` at `0x18007e923`
- `bcrypt!BCryptDestroyKey` at `0x18007e923`
- `ntdll!RtlNtStatusToDosError` at `0x18007e6e7`
- `ntdll!RtlNtStatusToDosError` at `0x18007e810`
- `ntdll!RtlNtStatusToDosError` at `0x18007e6e7`
- `ntdll!RtlNtStatusToDosError` at `0x18007e810`

## pseudocode

```c

```
