# Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)

- ea: `0x180029a54`
- end: `0x180029d27`
- name: `?CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `723`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800297c8`

## callees

- `0x1800197d4`
- `0x180029a54`
- `0x180029d30`
- `0x18004869c`
- `0x180059920`
- `0x18005a8bc`
- `0x180130010`

## import_xrefs

- `KERNEL32!K32GetProcessMemoryInfo` at `0x180029b04`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x180029b04`
- `KERNEL32!GetCurrentProcess` at `0x180029af3`
- `KERNEL32!GetCurrentProcess` at `0x180029af3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029ab5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180029ab5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029ac7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029c90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029cb2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029ac7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029c90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029cb2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029aed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029aed`
- `KERNEL32!GetLastError` at `0x180029b0e`
- `KERNEL32!GetLastError` at `0x180029b0e`

## string_xrefs

- `0x180029b21`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x180029ba1`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x180029c5f`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x180029b95`: `Commit size [%zu] is greater than the max requested %zu for %d sec`

## pseudocode

```c

```
