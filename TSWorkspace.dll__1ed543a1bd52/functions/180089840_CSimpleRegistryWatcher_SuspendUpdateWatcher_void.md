# CSimpleRegistryWatcher::SuspendUpdateWatcher(void)

- ea: `0x180089840`
- end: `0x180089906`
- name: `?SuspendUpdateWatcher@CSimpleRegistryWatcher@@IEAAJXZ`
- size: `198`
- prototype: `__int64 __fastcall(CSimpleRegistryWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180089038`

## callees

- `0x180089840`
- `0x180089b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089894`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898e9`

## string_xrefs

- `0x180089877`: `Update watcher is not running`

## pseudocode

```c

```
