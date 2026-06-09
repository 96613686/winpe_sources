# PhoneServiceListener::GetNotifyData(_PhoneNotifyData *,int *)

- ea: `0x18008cf8c`
- end: `0x18008d0de`
- name: `?GetNotifyData@PhoneServiceListener@@QEAAJPEAU_PhoneNotifyData@@PEAH@Z`
- size: `338`
- prototype: `__int64 __fastcall(PhoneServiceListener *__hidden this, struct _PhoneNotifyData *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18008acf0`

## callees

- `0x1800012b8`
- `0x1800056a0`
- `0x18007f9ec`
- `0x18008cf8c`
- `0x18008d0e4`
- `0x18008d0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008d098`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008d098`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008cfa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008cfa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008d0cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008d0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d0a2`

## string_xrefs

- `0x18008cff7`: `PhoneServiceListener: Phone service listener lost notifications`

## pseudocode

```c

```
