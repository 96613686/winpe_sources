# TelCacheProvider::BatchEnd(void)

- ea: `0x18010028c`
- end: `0x1801007f9`
- name: `?BatchEnd@TelCacheProvider@@QEAAJXZ`
- size: `1389`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180101fe0`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180013f90`
- `0x1800144c4`
- `0x18001a2f4`
- `0x1800287d4`
- `0x1800ff90c`
- `0x1800ff9d8`
- `0x18010028c`
- `0x180104040`
- `0x1801041fc`
- `0x180106120`
- `0x180107cf0`
- `0x1801090cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180100492`
- `KERNEL32!SetEvent` at `0x1801007ac`
- `KERNEL32!SetEvent` at `0x180100492`
- `KERNEL32!SetEvent` at `0x1801007ac`
- `KERNEL32!GetProcessHeap` at `0x1801002e2`
- `KERNEL32!GetProcessHeap` at `0x1801002e2`
- `KERNEL32!ReleaseMutex` at `0x180100488`
- `KERNEL32!ReleaseMutex` at `0x1801007a2`
- `KERNEL32!ReleaseMutex` at `0x180100488`
- `KERNEL32!ReleaseMutex` at `0x1801007a2`
- `KERNEL32!WaitForSingleObject` at `0x18010046f`
- `KERNEL32!WaitForSingleObject` at `0x18010078c`
- `KERNEL32!WaitForSingleObject` at `0x18010046f`
- `KERNEL32!WaitForSingleObject` at `0x18010078c`
- `KERNEL32!HeapFree` at `0x1801007ce`
- `KERNEL32!HeapFree` at `0x1801007ce`

## string_xrefs

- `0x1801003d0`: `InventoryCache::NextBatchMarkedItem failed. [%#x]`
- `0x1801006f6`: `IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]`
- `0x180100681`: `TelCacheProvider::GetItem failed. [%#x]`
- `0x1801005b1`: `InventoryCache::GetNextItem failed. [%#x]`
- `0x18010035c`: `TelCacheProvider::BatchEnd`
- `0x1801003b4`: `TelCacheProvider::BatchEnd`
- `0x1801004f7`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x180100732`: `InventoryCache::RemoveItem failed. [%#x]`

## pseudocode

```c

```
