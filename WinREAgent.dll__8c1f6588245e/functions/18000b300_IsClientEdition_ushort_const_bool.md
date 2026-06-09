# IsClientEdition(ushort const *,bool *)

- ea: `0x18000b300`
- end: `0x18000b534`
- name: `?IsClientEdition@@YAJPEBGPEA_N@Z`
- size: `564`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000dcc8`
- `0x18000ea90`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x18000b300`
- `0x18000d5c0`
- `0x18000d92c`
- `0x180037344`
- `0x180038448`
- `0x18006c652`
- `0x18006c65e`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18000b35a`
- `KERNEL32!GetVersionExW` at `0x18000b35a`
- `KERNEL32!GetLastError` at `0x18000b373`
- `KERNEL32!GetLastError` at `0x18000b3b5`
- `KERNEL32!GetLastError` at `0x18000b373`
- `KERNEL32!GetLastError` at `0x18000b3b5`

## string_xrefs

- `0x18000b39b`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b41b`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b4a7`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b477`: `InstallationType`
- `0x18000b493`: `Failed to get value of InstallationType`

## pseudocode

```c

```
