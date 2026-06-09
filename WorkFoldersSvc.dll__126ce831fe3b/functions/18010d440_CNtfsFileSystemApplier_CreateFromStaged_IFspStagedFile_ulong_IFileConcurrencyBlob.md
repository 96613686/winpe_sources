# CNtfsFileSystemApplier::CreateFromStaged(IFspStagedFile *,ulong,IFileConcurrencyBlob * *)

- ea: `0x18010d440`
- end: `0x18010d732`
- name: `?CreateFromStaged@CNtfsFileSystemApplier@@AEAAJPEAUIFspStagedFile@@KPEAPEAUIFileConcurrencyBlob@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IFspStagedFile *, __int64, struct IFileConcurrencyBlob **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18010d280`

## callees

- `0x180007e10`
- `0x180009188`
- `0x1800091ac`
- `0x180011314`
- `0x180058d88`
- `0x1800bb298`
- `0x1800bb748`
- `0x18010d440`
- `0x18010e084`
- `0x18010e38c`
- `0x18010fd2c`
- `0x180111b4c`
- `0x18013e010`

## import_xrefs

- `ntdll!NtClose` at `0x18010d696`
- `ntdll!NtClose` at `0x18010d6f4`
- `ntdll!NtClose` at `0x18010d696`
- `ntdll!NtClose` at `0x18010d6f4`

## string_xrefs

- `0x18010d4c1`: `CNtfsFileSystemApplier::CreateFromStaged`

## pseudocode

```c

```
