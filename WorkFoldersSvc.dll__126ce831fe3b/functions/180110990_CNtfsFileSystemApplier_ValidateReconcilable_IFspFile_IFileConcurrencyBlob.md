# CNtfsFileSystemApplier::ValidateReconcilable(IFspFile *,IFileConcurrencyBlob * *)

- ea: `0x180110990`
- end: `0x180110c5b`
- name: `?ValidateReconcilable@CNtfsFileSystemApplier@@AEAAJPEAUIFspFile@@PEAPEAUIFileConcurrencyBlob@@@Z`
- size: `715`
- prototype: `int(CNtfsFileSystemApplier *__hidden this, struct IFspFile *, struct IFileConcurrencyBlob **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010f360`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180011314`
- `0x180058d88`
- `0x18009d66c`
- `0x1800bb594`
- `0x180110990`
- `0x18011263c`
- `0x180112aa0`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180110bb9`
- `KERNEL32!CompareFileTime` at `0x180110bb9`
- `ntdll!NtClose` at `0x180110c1e`
- `ntdll!NtClose` at `0x180110c1e`

## pseudocode

```c

```
