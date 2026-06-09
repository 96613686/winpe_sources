# CSimpleRegistryWatcher::ResetRegKeyWatch(int)

- ea: `0x180089038`
- end: `0x1800892ae`
- name: `?ResetRegKeyWatch@CSimpleRegistryWatcher@@IEAAJH@Z`
- size: `630`
- prototype: `__int64 __fastcall(CSimpleRegistryWatcher *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800404c0`
- `0x180074bb8`

## callees

- `0x180089038`
- `0x1800892b4`
- `0x180089840`
- `0x180089b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089116`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891d1`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800890fc`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x180089146`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800890fc`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x180089146`

## string_xrefs

- `0x18008907a`: `Update watcher is not running`
- `0x1800890c8`: `"SuspendUpdateWatcher failed"`
- `0x180089293`: `"ResumeUpdateWatcher failed"`

## pseudocode

```c

```
