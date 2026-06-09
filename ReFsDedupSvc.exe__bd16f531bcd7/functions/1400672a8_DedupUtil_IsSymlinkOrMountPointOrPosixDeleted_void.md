# DedupUtil::IsSymlinkOrMountPointOrPosixDeleted(void *)

- ea: `0x1400672a8`
- end: `0x14006740a`
- name: `?IsSymlinkOrMountPointOrPosixDeleted@DedupUtil@@YA_NPEAX@Z`
- size: `354`
- prototype: `bool __fastcall(HANDLE hDevice, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x140077050`
- `0x140077864`

## callees

- `0x140004870`
- `0x140019600`
- `0x14001983c`
- `0x140063bbc`
- `0x1400649f8`
- `0x140064c40`
- `0x1400662f4`
- `0x1400672a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140067327`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140067327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067389`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1400672ef`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1400672ef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140067365`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140067365`

## string_xrefs

- `0x1400673c0`: `Unable to read reparse point for %s, error = 0x%x\n`

## pseudocode

```c

```
