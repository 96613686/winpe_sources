# Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)

- ea: `0x18000fb70`
- end: `0x18000fbec`
- name: `?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f3b4`
- `0x18000f700`
- `0x18000f8ec`
- `0x18000f950`
- `0x180045740`
- `0x18004eda4`
- `0x18010dd08`

## callees

- `0x18000fb70`

## import_xrefs

- `KERNEL32!SignalObjectAndWait` at `0x18000fbcf`
- `KERNEL32!SignalObjectAndWait` at `0x18000fbcf`
- `KERNEL32!WaitForSingleObject` at `0x18000fb91`
- `KERNEL32!WaitForSingleObject` at `0x18000fbdb`
- `KERNEL32!WaitForSingleObject` at `0x18000fb91`
- `KERNEL32!WaitForSingleObject` at `0x18000fbdb`
- `KERNEL32!ReleaseMutex` at `0x18000fbb2`

## pseudocode

```c

```
