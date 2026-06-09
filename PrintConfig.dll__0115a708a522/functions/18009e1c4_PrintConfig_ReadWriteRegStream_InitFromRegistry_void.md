# PrintConfig::ReadWriteRegStream::InitFromRegistry(void)

- ea: `0x18009e1c4`
- end: `0x18009e48b`
- name: `?InitFromRegistry@ReadWriteRegStream@PrintConfig@@AEAAXXZ`
- size: `711`
- prototype: `void __fastcall(PrintConfig::ReadWriteRegStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009e070`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800197b4`
- `0x18009e1c4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009e2b5`
- `KERNEL32!GetLastError` at `0x18009e2b5`
- `KERNEL32!GlobalLock` at `0x18009e29d`
- `KERNEL32!GlobalLock` at `0x18009e29d`
- `KERNEL32!GlobalUnlock` at `0x18009e320`
- `KERNEL32!GlobalUnlock` at `0x18009e320`
- `ADVAPI32!RegQueryValueExW` at `0x18009e221`
- `ADVAPI32!RegQueryValueExW` at `0x18009e2fe`
- `ADVAPI32!RegQueryValueExW` at `0x18009e221`
- `ADVAPI32!RegQueryValueExW` at `0x18009e2fe`
- `ole32!GetHGlobalFromStream` at `0x18009e27c`
- `ole32!GetHGlobalFromStream` at `0x18009e27c`

## pseudocode

```c

```
