# Print::Driver::Config::PrinterDriverWinSpool::ConvertPidToProcessName(ulong,ushort *,ulong)

- ea: `0x18005b690`
- end: `0x18005b92c`
- name: `?ConvertPidToProcessName@PrinterDriverWinSpool@Config@Driver@Print@@CAXKPEAGK@Z`
- size: `668`
- prototype: `void __fastcall(DWORD dwProcessId, LPWSTR lpFilename, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18005bfc0`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800197b4`
- `0x18005b690`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18005b6f1`
- `KERNEL32!GetProcAddress` at `0x18005b6f1`
- `KERNEL32!FreeLibrary` at `0x18005b7c4`
- `KERNEL32!FreeLibrary` at `0x18005b7c4`
- `KERNEL32!CloseHandle` at `0x18005b7a8`
- `KERNEL32!CloseHandle` at `0x18005b7a8`
- `KERNEL32!GetLastError` at `0x18005b733`
- `KERNEL32!GetLastError` at `0x18005b775`
- `KERNEL32!GetLastError` at `0x18005b7f0`
- `KERNEL32!GetLastError` at `0x18005b733`
- `KERNEL32!GetLastError` at `0x18005b775`
- `KERNEL32!GetLastError` at `0x18005b7f0`
- `KERNEL32!GetModuleFileNameW` at `0x18005b7e0`
- `KERNEL32!GetModuleFileNameW` at `0x18005b7e0`
- `KERNEL32!OpenProcess` at `0x18005b713`
- `KERNEL32!OpenProcess` at `0x18005b713`

## string_xrefs

- `0x18005b6d2`: `kernel32.dll`

## pseudocode

```c

```
