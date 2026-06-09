# CSystemMSIDescriptor::Install(int *)

- ea: `0x18003291c`
- end: `0x180032a7d`
- name: `?Install@CSystemMSIDescriptor@@QEAAJPEAH@Z`
- size: `353`
- prototype: `__int64 __fastcall(CSystemMSIDescriptor *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18003f7f0`

## callees

- `0x180007828`
- `0x18000791c`
- `0x18003291c`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180032a02`
- `SHELL32!ShellExecuteExW` at `0x180032a02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032a13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032a13`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180032a2a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180032a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a53`

## string_xrefs

- `0x180032994`: ` /norestart /uninstall`

## pseudocode

```c

```
