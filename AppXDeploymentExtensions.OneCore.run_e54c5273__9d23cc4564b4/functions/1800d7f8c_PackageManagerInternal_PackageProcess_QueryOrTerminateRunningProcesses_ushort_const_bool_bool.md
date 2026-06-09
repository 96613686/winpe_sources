# PackageManagerInternal::PackageProcess::QueryOrTerminateRunningProcesses(ushort const *,bool,bool *)

- ea: `0x1800d7f8c`
- end: `0x1800d8185`
- name: `?QueryOrTerminateRunningProcesses@PackageProcess@PackageManagerInternal@@CAJPEBG_NPEA_N@Z`
- size: `505`
- prototype: `__int64 __fastcall(LPCWCH lpString1, bool, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800d7f58`

## callees

- `0x18000e684`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800d7f8c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d80e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d80e0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800d80ce`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800d80ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d80f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d80f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d806b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d806b`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1800d8023`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1800d8023`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1800d8097`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1800d8097`

## string_xrefs

- `0x1800d8117`: `onecore\admin\appmodel\common\packageprocess.cpp`
- `0x1800d8146`: `onecore\admin\appmodel\common\packageprocess.cpp`

## pseudocode

```c

```
