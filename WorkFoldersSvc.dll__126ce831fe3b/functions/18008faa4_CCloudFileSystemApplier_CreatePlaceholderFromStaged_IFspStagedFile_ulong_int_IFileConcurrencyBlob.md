# CCloudFileSystemApplier::CreatePlaceholderFromStaged(IFspStagedFile *,ulong,int,IFileConcurrencyBlob * *)

- ea: `0x18008faa4`
- end: `0x18008fd4c`
- name: `?CreatePlaceholderFromStaged@CCloudFileSystemApplier@@AEAAJPEAUIFspStagedFile@@KHPEAPEAUIFileConcurrencyBlob@@@Z`
- size: `680`
- prototype: `__int64 __usercall@<rax>(CCloudFileSystemApplier *__hidden this@<rcx>, struct IFspStagedFile *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct IFileConcurrencyBlob **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18008f1b8`

## callees

- `0x180007e10`
- `0x1800091ac`
- `0x180011314`
- `0x180058d88`
- `0x18008faa4`
- `0x1800908d8`
- `0x1800950b4`
- `0x180098eec`
- `0x1800bb298`
- `0x1800bb748`
- `0x18013e010`

## import_xrefs

- `ntdll!NtClose` at `0x18008fc8f`
- `ntdll!NtClose` at `0x18008fce8`
- `ntdll!NtClose` at `0x18008fc8f`
- `ntdll!NtClose` at `0x18008fce8`

## string_xrefs

- `0x18008fb28`: `CCloudFileSystemApplier::CreatePlaceholderFromStaged`

## pseudocode

```c

```
