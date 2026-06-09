# InitJobObject(void *)

- ea: `0x18001bb50`
- end: `0x18001bc3d`
- name: `?InitJobObject@@YAPEAXPEAX@Z`
- size: `237`
- prototype: `void *__fastcall(HANDLE hJob)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bc50`

## callees

- `0x18001bb50`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc0f`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001bbd3`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001bbd3`
- `KERNEL32!QueryInformationJobObject` at `0x18001bba0`
- `KERNEL32!QueryInformationJobObject` at `0x18001bba0`
- `KERNEL32!SetInformationJobObject` at `0x18001bbbe`
- `KERNEL32!SetInformationJobObject` at `0x18001bbfd`
- `KERNEL32!SetInformationJobObject` at `0x18001bbbe`
- `KERNEL32!SetInformationJobObject` at `0x18001bbfd`

## pseudocode

```c

```
