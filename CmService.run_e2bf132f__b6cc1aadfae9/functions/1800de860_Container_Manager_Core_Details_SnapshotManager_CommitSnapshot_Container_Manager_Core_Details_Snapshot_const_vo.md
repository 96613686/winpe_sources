# Container::Manager::Core::Details::SnapshotManager::CommitSnapshot(Container::Manager::Core::Details::Snapshot const &,void *)

- ea: `0x1800de860`
- end: `0x1800debfe`
- name: `?CommitSnapshot@SnapshotManager@Details@Core@Manager@Container@@QEAAJAEBVSnapshot@2345@PEAX@Z`
- size: `926`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::SnapshotManager *__hidden this, const struct Container::Manager::Core::Details::Snapshot *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180053648`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x18002c5b4`
- `0x180032344`
- `0x1800343f0`
- `0x180034674`
- `0x1800346e8`
- `0x180034918`
- `0x18006cda4`
- `0x1800de860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de90f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de92e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de92e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800de920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dea00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dea1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800debc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800de920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dea00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dea1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800debc2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800de947`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800de947`

## string_xrefs

- `0x1800de970`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x1800de964`: `Failed to delete subkey with name '%ws'`

## pseudocode

```c

```
