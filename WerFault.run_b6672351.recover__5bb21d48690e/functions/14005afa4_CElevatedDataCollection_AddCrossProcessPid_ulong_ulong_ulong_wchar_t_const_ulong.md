# CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)

- ea: `0x14005afa4`
- end: `0x14005b213`
- name: `?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z`
- size: `623`
- prototype: `__int64 __usercall@<rax>(CElevatedDataCollection *__hidden this@<rcx>, DWORD dwProcessId@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, const wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140024924`
- `0x14005ba44`
- `0x14005cbac`
- `0x14005d808`

## callees

- `0x14000333f`
- `0x140003357`
- `0x140003393`
- `0x14000339f`
- `0x140014ee4`
- `0x140014f14`
- `0x14005afa4`
- `0x14005de78`
- `0x14005ef38`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b1d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b1d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b1ed`

## string_xrefs

- `0x14005b100`: `Open process failed unexpectedly: 0X%X`
- `0x14005afd7`: `Attempting to cross-proc reporting process!`

## pseudocode

```c

```
