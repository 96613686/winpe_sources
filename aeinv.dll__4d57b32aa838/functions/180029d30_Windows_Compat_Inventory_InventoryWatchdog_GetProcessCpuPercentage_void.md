# Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage(void)

- ea: `0x180029d30`
- end: `0x180029f6a`
- name: `?GetProcessCpuPercentage@InventoryWatchdog@Inventory@Compat@Windows@@CAMXZ`
- size: `570`
- prototype: `float(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029a54`

## callees

- `0x1800197d4`
- `0x180029d30`
- `0x180067adc`

## import_xrefs

- `KERNEL32!GetActiveProcessorCount` at `0x180029e0f`
- `KERNEL32!GetActiveProcessorCount` at `0x180029e0f`
- `KERNEL32!GetProcessTimes` at `0x180029db0`
- `KERNEL32!GetProcessTimes` at `0x180029e77`
- `KERNEL32!GetProcessTimes` at `0x180029db0`
- `KERNEL32!GetProcessTimes` at `0x180029e77`
- `KERNEL32!GetCurrentProcess` at `0x180029d92`
- `KERNEL32!GetCurrentProcess` at `0x180029e59`
- `KERNEL32!GetCurrentProcess` at `0x180029d92`
- `KERNEL32!GetCurrentProcess` at `0x180029e59`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029d61`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029e4f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029d61`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029e4f`
- `KERNEL32!GetLastError` at `0x180029dba`
- `KERNEL32!GetLastError` at `0x180029e81`
- `KERNEL32!GetLastError` at `0x180029dba`
- `KERNEL32!GetLastError` at `0x180029e81`

## string_xrefs

- `0x180029dcd`: `Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage`
- `0x180029e94`: `Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage`

## pseudocode

```c

```
