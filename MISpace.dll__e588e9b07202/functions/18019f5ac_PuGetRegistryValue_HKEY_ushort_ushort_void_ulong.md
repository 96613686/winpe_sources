# PuGetRegistryValue(HKEY__ *,ushort *,ushort *,void * *,ulong *)

- ea: `0x18019f5ac`
- end: `0x18019f6ec`
- name: `?PuGetRegistryValue@@YAHPEAUHKEY__@@PEAG1PEAPEAXPEAK@Z`
- size: `320`
- prototype: `int(HKEY, unsigned __int16 *, unsigned __int16 *, void **, unsigned int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18019bfd8`
- `0x18019ebe8`
- `0x18019f850`
- `0x1801a02d4`
- `0x1801a0df0`

## callees

- `0x18019f5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f609`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f6d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019f6d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f63f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f6bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f63f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019f6bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019f659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019f659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f6b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f6b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f5fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f5fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019f631`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019f68b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019f631`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18019f68b`

## pseudocode

```c

```
