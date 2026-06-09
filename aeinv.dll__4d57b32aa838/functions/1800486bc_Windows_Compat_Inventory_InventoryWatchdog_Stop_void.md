# Windows::Compat::Inventory::InventoryWatchdog::Stop(void)

- ea: `0x1800486bc`
- end: `0x1800487a5`
- name: `?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ`
- size: `233`
- prototype: `bool __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180048468`
- `0x18005e788`

## callees

- `0x1800197d4`
- `0x1800407d8`
- `0x1800486bc`
- `0x180048ad0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18004872b`
- `KERNEL32!WaitForSingleObject` at `0x18004872b`
- `KERNEL32!SetEvent` at `0x1800486e3`
- `KERNEL32!SetEvent` at `0x1800486e3`
- `KERNEL32!GetLastError` at `0x1800486f0`
- `KERNEL32!GetLastError` at `0x180048745`
- `KERNEL32!GetLastError` at `0x1800486f0`
- `KERNEL32!GetLastError` at `0x180048745`

## string_xrefs

- `0x180048703`: `Windows::Compat::Inventory::InventoryWatchdog::Stop`
- `0x180048763`: `Windows::Compat::Inventory::InventoryWatchdog::Stop`

## pseudocode

```c

```
