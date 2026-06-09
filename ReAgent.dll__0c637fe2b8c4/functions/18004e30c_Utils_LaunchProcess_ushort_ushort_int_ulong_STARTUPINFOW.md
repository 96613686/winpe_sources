# Utils::LaunchProcess(ushort *,ushort *,int,ulong *,_STARTUPINFOW *)

- ea: `0x18004e30c`
- end: `0x18004e4e9`
- name: `?LaunchProcess@Utils@@SAKPEAG0HPEAKPEAU_STARTUPINFOW@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001dc60`

## callees

- `0x18004e30c`
- `0x18004e5a0`
- `0x18004f8d0`
- `0x18004fb7c`
- `0x18004fc28`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetExitCodeProcess` at `0x18004e471`
- `KERNEL32!GetExitCodeProcess` at `0x18004e471`
- `KERNEL32!GetLastError` at `0x18004e3d4`
- `KERNEL32!GetLastError` at `0x18004e443`
- `KERNEL32!GetLastError` at `0x18004e47b`
- `KERNEL32!GetLastError` at `0x18004e3d4`
- `KERNEL32!GetLastError` at `0x18004e443`
- `KERNEL32!GetLastError` at `0x18004e47b`
- `KERNEL32!CreateProcessW` at `0x18004e3ca`
- `KERNEL32!CreateProcessW` at `0x18004e3ca`
- `KERNEL32!CloseHandle` at `0x18004e4b2`
- `KERNEL32!CloseHandle` at `0x18004e4bd`
- `KERNEL32!CloseHandle` at `0x18004e4b2`
- `KERNEL32!CloseHandle` at `0x18004e4bd`
- `KERNEL32!WaitForSingleObject` at `0x18004e437`
- `KERNEL32!WaitForSingleObject` at `0x18004e437`

## pseudocode

```c

```
