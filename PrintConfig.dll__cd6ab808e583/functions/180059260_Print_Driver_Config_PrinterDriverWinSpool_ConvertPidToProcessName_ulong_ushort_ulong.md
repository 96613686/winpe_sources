# Print::Driver::Config::PrinterDriverWinSpool::ConvertPidToProcessName(ulong,ushort *,ulong)

- ea: `0x180059260`
- end: `0x1800594cb`
- name: `?ConvertPidToProcessName@PrinterDriverWinSpool@Config@Driver@Print@@CAXKPEAGK@Z`
- size: `619`
- prototype: `void __fastcall(DWORD dwProcessId, LPWSTR lpFilename, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180059b50`

## callees

- `0x180004424`
- `0x18000f380`
- `0x180018bbc`
- `0x180059260`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800592c1`
- `KERNEL32!GetProcAddress` at `0x1800592c1`
- `KERNEL32!FreeLibrary` at `0x180059376`
- `KERNEL32!FreeLibrary` at `0x180059376`
- `KERNEL32!CloseHandle` at `0x180059360`
- `KERNEL32!CloseHandle` at `0x180059360`
- `KERNEL32!GetLastError` at `0x1800592f7`
- `KERNEL32!GetLastError` at `0x180059333`
- `KERNEL32!GetLastError` at `0x180059396`
- `KERNEL32!GetLastError` at `0x1800592f7`
- `KERNEL32!GetLastError` at `0x180059333`
- `KERNEL32!GetLastError` at `0x180059396`
- `KERNEL32!GetModuleFileNameW` at `0x18005938c`
- `KERNEL32!GetModuleFileNameW` at `0x18005938c`
- `KERNEL32!OpenProcess` at `0x1800592dd`
- `KERNEL32!OpenProcess` at `0x1800592dd`

## string_xrefs

- `0x1800592a2`: `kernel32.dll`

## pseudocode

```c

```
