# CNTService::ParseStandardArgs(int,ushort * * const)

- ea: `0x14005db60`
- end: `0x14005dcaf`
- name: `?ParseStandardArgs@CNTService@@QEAAHHQEAPEAG@Z`
- size: `335`
- prototype: `__int64 __fastcall(CNTService *__hidden this, int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x140046260`

## callees

- `0x14005d9a0`
- `0x14005db60`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14005dc4f`
- `KERNEL32!GetModuleFileNameW` at `0x14005dc4f`
- `KERNEL32!GetLastError` at `0x14005dbd8`
- `KERNEL32!GetLastError` at `0x14005dc6c`
- `KERNEL32!GetLastError` at `0x14005dbd8`
- `KERNEL32!GetLastError` at `0x14005dc6c`
- `msvcrt!_wcsicmp` at `0x14005db99`
- `msvcrt!_wcsicmp` at `0x14005dbf5`
- `msvcrt!_wcsicmp` at `0x14005db99`
- `msvcrt!_wcsicmp` at `0x14005dbf5`
- `msvcrt!wprintf` at `0x14005dc1d`
- `msvcrt!wprintf` at `0x14005dc64`
- `msvcrt!wprintf` at `0x14005dc7f`
- `msvcrt!wprintf` at `0x14005dc1d`
- `msvcrt!wprintf` at `0x14005dc64`
- `msvcrt!wprintf` at `0x14005dc7f`

## string_xrefs

- `0x14005dbb3`: `%ls is already installed\n`
- `0x14005dbcf`: `%ls installed\n`
- `0x14005dbde`: `l%s failed to install. Error %d\n`
- `0x14005dc13`: `%ls is not installed\n`
- `0x14005dc5d`: `%ls removed. (You must delete the file (%s) yourself.)\n`
- `0x14005dc72`: `Could not remove %ls. Error %d\n`

## pseudocode

```c

```
