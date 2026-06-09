# Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)

- ea: `0x18002abc4`
- end: `0x18002ae95`
- name: `?CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `721`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002ff3c`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18001a2f4`
- `0x18002abc4`
- `0x18002c120`
- `0x18021f010`

## import_xrefs

- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002ac74`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002ac74`
- `KERNEL32!GetCurrentProcess` at `0x18002ac63`
- `KERNEL32!GetCurrentProcess` at `0x18002ac63`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ac25`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ac25`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ac37`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ae00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ae21`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ac37`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ae00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ae21`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ac5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ae12`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ae34`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ac5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ae12`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002ae34`
- `KERNEL32!GetLastError` at `0x18002ac7e`
- `KERNEL32!GetLastError` at `0x18002ac7e`

## string_xrefs

- `0x18002ad05`: `Commit size [%zu] is greater than the max requested %zu for %d sec`
- `0x18002ac91`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x18002ad11`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x18002adcf`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`

## pseudocode

```c

```
