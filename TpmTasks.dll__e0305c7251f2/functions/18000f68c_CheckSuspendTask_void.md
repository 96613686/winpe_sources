# CheckSuspendTask(void)

- ea: `0x18000f68c`
- end: `0x18000f797`
- name: `?CheckSuspendTask@@YAXXZ`
- size: `267`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000f68c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000f707`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000f707`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f76f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f76f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f753`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f753`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f760`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f760`

## string_xrefs

- `0x18000f6e2`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x18000f71f`: `TpmTaskSuspendForDebugger`

## pseudocode

```c

```
