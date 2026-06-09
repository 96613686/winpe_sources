# CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)

- ea: `0x140057238`
- end: `0x14005749a`
- name: `?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z`
- size: `610`
- prototype: `__int64 __fastcall(CElevatedDataCollection *this, DWORD dwProcessId, int, int, const wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140023204`
- `0x140057cb0`
- `0x140058de0`
- `0x140059a10`

## callees

- `0x1400032ef`
- `0x140003307`
- `0x140003343`
- `0x14000334f`
- `0x14001444c`
- `0x140014474`
- `0x140057238`
- `0x14005a074`
- `0x14005b198`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005747b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005747b`

## string_xrefs

- `0x14005726b`: `Attempting to cross-proc reporting process!`
- `0x140057394`: `Open process failed unexpectedly: 0X%X`

## pseudocode

```c

```
