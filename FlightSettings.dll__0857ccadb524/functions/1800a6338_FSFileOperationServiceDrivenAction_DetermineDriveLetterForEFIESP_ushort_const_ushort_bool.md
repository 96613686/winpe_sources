# FSFileOperationServiceDrivenAction::DetermineDriveLetterForEFIESP(ushort const *,ushort *,bool *)

- ea: `0x1800a6338`
- end: `0x1800a645e`
- name: `?DetermineDriveLetterForEFIESP@FSFileOperationServiceDrivenAction@@CAJPEBGPEAGPEA_N@Z`
- size: `294`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800a6fa0`

## callees

- `0x180004b80`
- `0x180005744`
- `0x1800a6338`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a63aa`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a63aa`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800a63d4`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800a6429`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800a63d4`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800a6429`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800a63f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800a63f9`

## pseudocode

```c

```
