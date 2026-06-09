# Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage(void)

- ea: `0x18002c120`
- end: `0x18002c35a`
- name: `?GetProcessCpuPercentage@InventoryWatchdog@Inventory@Compat@Windows@@CAMXZ`
- size: `570`
- prototype: `float(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002abc4`

## callees

- `0x18001a2f4`
- `0x18002c120`
- `0x180030730`

## import_xrefs

- `KERNEL32!GetActiveProcessorCount` at `0x18002c1ff`
- `KERNEL32!GetActiveProcessorCount` at `0x18002c1ff`
- `KERNEL32!GetProcessTimes` at `0x18002c1a0`
- `KERNEL32!GetProcessTimes` at `0x18002c267`
- `KERNEL32!GetProcessTimes` at `0x18002c1a0`
- `KERNEL32!GetProcessTimes` at `0x18002c267`
- `KERNEL32!GetCurrentProcess` at `0x18002c182`
- `KERNEL32!GetCurrentProcess` at `0x18002c249`
- `KERNEL32!GetCurrentProcess` at `0x18002c182`
- `KERNEL32!GetCurrentProcess` at `0x18002c249`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002c151`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002c23f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002c151`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002c23f`
- `KERNEL32!GetLastError` at `0x18002c1aa`
- `KERNEL32!GetLastError` at `0x18002c271`
- `KERNEL32!GetLastError` at `0x18002c1aa`
- `KERNEL32!GetLastError` at `0x18002c271`

## string_xrefs

- `0x18002c1bd`: `Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage`
- `0x18002c284`: `Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage`

## pseudocode

```c

```
