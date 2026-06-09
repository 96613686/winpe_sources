# CRegistryMonitor::ThreadProc(void)

- ea: `0x1800a4ef0`
- end: `0x1800a534d`
- name: `?ThreadProc@CRegistryMonitor@@EEAAJXZ`
- size: `1117`
- prototype: `__int64 __fastcall(CRegistryMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18002a334`
- `0x1800a4ef0`
- `0x18010215c`
- `0x180129620`
- `0x180129678`
- `0x180688f1a`
- `0x180688f3e`
- `0x18068c010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800a5188`
- `KERNEL32!SetEvent` at `0x1800a531a`
- `KERNEL32!SetEvent` at `0x1800a5188`
- `KERNEL32!SetEvent` at `0x1800a531a`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a519d`
- `KERNEL32!WaitForMultipleObjects` at `0x1800a519d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a5006`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a5006`
- `ADVAPI32!RegQueryValueExW` at `0x1800a50a7`
- `ADVAPI32!RegQueryValueExW` at `0x1800a51dc`
- `ADVAPI32!RegQueryValueExW` at `0x1800a50a7`
- `ADVAPI32!RegQueryValueExW` at `0x1800a51dc`
- `ADVAPI32!RegCloseKey` at `0x1800a5308`
- `ADVAPI32!RegCloseKey` at `0x1800a5308`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800a5137`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800a52b8`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800a5137`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1800a52b8`

## pseudocode

```c

```
