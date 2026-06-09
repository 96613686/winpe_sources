# Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)

- ea: `0x18000fbf4`
- end: `0x18000fcc6`
- name: `?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ`
- size: `210`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f3b4`
- `0x18002da48`
- `0x18002debc`
- `0x180045740`
- `0x18004ec54`
- `0x18004f744`
- `0x18005113c`
- `0x18005f210`
- `0x180064f04`
- `0x1800658d4`
- `0x180066814`

## callees

- `0x18000fbf4`

## import_xrefs

- `KERNEL32!SignalObjectAndWait` at `0x18000fc8c`
- `KERNEL32!SignalObjectAndWait` at `0x18000fc8c`
- `KERNEL32!WaitForSingleObject` at `0x18000fc21`
- `KERNEL32!WaitForSingleObject` at `0x18000fc9d`
- `KERNEL32!WaitForSingleObject` at `0x18000fc21`
- `KERNEL32!WaitForSingleObject` at `0x18000fc9d`
- `KERNEL32!ReleaseMutex` at `0x18000fc51`
- `KERNEL32!ReleaseMutex` at `0x18000fc51`

## pseudocode

```c

```
