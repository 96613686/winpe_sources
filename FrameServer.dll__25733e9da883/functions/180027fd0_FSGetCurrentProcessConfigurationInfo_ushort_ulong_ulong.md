# FSGetCurrentProcessConfigurationInfo(ushort *,ulong,ulong *)

- ea: `0x180027fd0`
- end: `0x1800281ff`
- name: `?FSGetCurrentProcessConfigurationInfo@@YAJPEAGKPEAK@Z`
- size: `559`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180030f00`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180007bcc`
- `0x180009608`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x18002763c`
- `0x180027fd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800280a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800280a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028132`
- `ntdll!NtQueryInformationProcess` at `0x1800280c5`
- `ntdll!NtQueryInformationProcess` at `0x180028150`
- `ntdll!NtQueryInformationProcess` at `0x1800280c5`
- `ntdll!NtQueryInformationProcess` at `0x180028150`

## pseudocode

```c

```
