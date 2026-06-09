# DrivePathFromDevicePathHelper::QueryDosDevices(void)

- ea: `0x18003cdd4`
- end: `0x18003cff6`
- name: `?QueryDosDevices@DrivePathFromDevicePathHelper@@AEAAKXZ`
- size: `546`
- prototype: `unsigned int __fastcall(DrivePathFromDevicePathHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004bc28`

## callees

- `0x180012920`
- `0x18003cdd4`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003ce8b`
- `ntdll!RtlFreeHeap` at `0x18003ce8b`
- `ntdll!RtlReAllocateHeap` at `0x18003cf33`
- `ntdll!RtlReAllocateHeap` at `0x18003cf33`
- `ntdll!RtlAllocateHeap` at `0x18003ce28`
- `ntdll!RtlAllocateHeap` at `0x18003cf13`
- `ntdll!RtlAllocateHeap` at `0x18003ce28`
- `ntdll!RtlAllocateHeap` at `0x18003cf13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce52`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003ce48`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003ce48`

## string_xrefs

- `0x18003ce65`: `DrivePathFromDevicePathHelper::QueryDosDevices`
- `0x18003cfa6`: `DrivePathFromDevicePathHelper::QueryDosDevices`

## pseudocode

```c

```
