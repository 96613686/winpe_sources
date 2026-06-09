# WmiThread<ulong>::AlertableWait(WmiTask<ulong> &,ulong const &)

- ea: `0x14002c728`
- end: `0x14002c98b`
- name: `?AlertableWait@?$WmiThread@K@@AEAA?AW4WmiStatusCode@@AEAV?$WmiTask@K@@AEBK@Z`
- size: `611`
- prototype: `__int64 __fastcall(__int64, __int64, DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x14002c5ac`

## callees

- `0x140021b24`
- `0x140026570`
- `0x14002a008`
- `0x14002ba53`
- `0x14002c728`
- `0x140046430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14002c8d5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14002c8d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c83b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c83b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c902`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002c850`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002c850`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14002c892`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14002c892`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x14002c882`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x14002c882`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x14002c8b8`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x14002c8b8`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x14002c89d`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x14002c89d`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14002c7f6`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14002c7f6`

## pseudocode

```c

```
