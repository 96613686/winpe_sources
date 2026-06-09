# Common::Deployment::PrefetchFile(ushort const *)

- ea: `0x18018ad90`
- end: `0x18018af6f`
- name: `?PrefetchFile@Deployment@Common@@YAJPEBG@Z`
- size: `479`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004057c`

## callees

- `0x18000669c`
- `0x18003bea4`
- `0x180081838`
- `0x18018ad90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018add5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18018add5`
- `ntdll!NtSetInformationVirtualMemory` at `0x18018aefc`
- `ntdll!NtSetInformationVirtualMemory` at `0x18018aefc`
- `KERNEL32!CreateFileMappingW` at `0x18018ae79`
- `KERNEL32!CreateFileMappingW` at `0x18018ae79`
- `KERNEL32!MapViewOfFile` at `0x18018aebd`
- `KERNEL32!MapViewOfFile` at `0x18018aebd`
- `KERNEL32!UnmapViewOfFile` at `0x18018af18`
- `KERNEL32!UnmapViewOfFile` at `0x18018af18`
- `KERNEL32!GetFileSizeEx` at `0x18018ae0c`
- `KERNEL32!GetFileSizeEx` at `0x18018ae0c`

## string_xrefs

- `0x18018ae20`: `onecore\admin\appmodel\common\prefetchfile.cpp`

## pseudocode

```c

```
