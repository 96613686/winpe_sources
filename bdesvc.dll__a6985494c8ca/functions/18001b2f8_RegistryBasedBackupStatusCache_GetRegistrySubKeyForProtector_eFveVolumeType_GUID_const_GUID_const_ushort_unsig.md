# RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(eFveVolumeType,_GUID const *,_GUID const *,ushort *,unsigned __int64)

- ea: `0x18001b2f8`
- end: `0x18001b4de`
- name: `?GetRegistrySubKeyForProtector@RegistryBasedBackupStatusCache@@AEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAG_K@Z`
- size: `486`
- prototype: `int __high(enum eFveVolumeType, const struct _GUID *, const struct _GUID *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180073cd0`

## callees

- `0x180009f60`
- `0x18001b2f8`
- `0x18001b7f0`
- `0x180034d28`
- `0x18007e010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001b4b2`
- `ntdll!RtlFreeUnicodeString` at `0x18001b4c3`
- `ntdll!RtlFreeUnicodeString` at `0x18001b4b2`
- `ntdll!RtlFreeUnicodeString` at `0x18001b4c3`
- `ntdll!RtlNtStatusToDosError` at `0x18001b34a`
- `ntdll!RtlNtStatusToDosError` at `0x18001b3b8`
- `ntdll!RtlNtStatusToDosError` at `0x18001b34a`
- `ntdll!RtlNtStatusToDosError` at `0x18001b3b8`
- `ntdll!RtlStringFromGUID` at `0x18001b33c`
- `ntdll!RtlStringFromGUID` at `0x18001b3aa`
- `ntdll!RtlStringFromGUID` at `0x18001b33c`
- `ntdll!RtlStringFromGUID` at `0x18001b3aa`

## pseudocode

```c

```
