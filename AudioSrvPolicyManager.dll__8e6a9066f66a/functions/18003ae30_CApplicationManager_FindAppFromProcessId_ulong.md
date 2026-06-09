# CApplicationManager::FindAppFromProcessId(ulong)

- ea: `0x18003ae30`
- end: `0x18003aef9`
- name: `?FindAppFromProcessId@CApplicationManager@@QEAAPEAVCApplication@@K@Z`
- size: `201`
- prototype: `struct CApplication *__fastcall(CApplicationManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180042b54`

## callees

- `0x18001b080`
- `0x18001b750`
- `0x18003ae30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aedf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aedf`

## pseudocode

```c

```
