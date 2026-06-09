# PrintConfig::ReadWriteRegStream::CommitToRegistry(void)

- ea: `0x18009cd80`
- end: `0x18009cf8d`
- name: `?CommitToRegistry@ReadWriteRegStream@PrintConfig@@AEAAXXZ`
- size: `525`
- prototype: `void __fastcall(PrintConfig::ReadWriteRegStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009cb8c`
- `0x18009cd40`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800197b4`
- `0x18009cd80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009cde5`
- `KERNEL32!GetLastError` at `0x18009cde5`
- `KERNEL32!GlobalSize` at `0x18009ce09`
- `KERNEL32!GlobalSize` at `0x18009ce09`
- `KERNEL32!GlobalLock` at `0x18009cdcd`
- `KERNEL32!GlobalLock` at `0x18009cdcd`
- `KERNEL32!GlobalUnlock` at `0x18009ce6c`
- `KERNEL32!GlobalUnlock` at `0x18009ce6c`
- `ADVAPI32!RegSetValueExW` at `0x18009ce4a`
- `ADVAPI32!RegSetValueExW` at `0x18009ce4a`
- `ole32!GetHGlobalFromStream` at `0x18009cdac`
- `ole32!GetHGlobalFromStream` at `0x18009cdac`

## pseudocode

```c

```
