# Windows::Compat::Inventory::InventoryWatchdog::Watch(void)

- ea: `0x18002ff3c`
- end: `0x1800301ca`
- name: `?Watch@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `654`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f5a0`

## callees

- `0x18001a2f4`
- `0x18002abc4`
- `0x18002ff3c`
- `0x18021f010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002ff7d`
- `KERNEL32!SetEvent` at `0x18002ff7d`
- `KERNEL32!WaitForMultipleObjects` at `0x180030006`
- `KERNEL32!WaitForMultipleObjects` at `0x180030006`
- `KERNEL32!IsDebuggerPresent` at `0x18003002a`
- `KERNEL32!IsDebuggerPresent` at `0x18003002a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ffe1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003001f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ffe1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003001f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002fff1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003003c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030067`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002fff1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003003c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030067`
- `KERNEL32!GetLastError` at `0x18002ff87`
- `KERNEL32!GetLastError` at `0x18002ff87`

## string_xrefs

- `0x180030171`: `m_threadRunningEvent not initialized [%#x]`
- `0x1800300b4`: `Max lifetime process commit %zu bytes`
- `0x180030137`: `Avg lifetime process commit %zu bytes`
- `0x18002ffc5`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x18003009c`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800300c1`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180030119`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180030144`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x180030160`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800301a4`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`

## pseudocode

```c

```
