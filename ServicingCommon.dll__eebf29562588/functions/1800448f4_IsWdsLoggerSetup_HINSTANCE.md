# IsWdsLoggerSetup(HINSTANCE__ * *)

- ea: `0x1800448f4`
- end: `0x1800449de`
- name: `?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z`
- size: `234`
- prototype: `bool __fastcall(HINSTANCE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800461b0`
- `0x18007bdb0`

## callees

- `0x18001f660`
- `0x1800293a0`
- `0x18003e810`
- `0x1800448f4`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180044933`
- `KERNEL32!GetModuleHandleExW` at `0x180044933`
- `KERNEL32!GetProcAddress` at `0x18004494f`
- `KERNEL32!GetProcAddress` at `0x18004496a`
- `KERNEL32!GetProcAddress` at `0x18004494f`
- `KERNEL32!GetProcAddress` at `0x18004496a`

## string_xrefs

- `0x18004492a`: `wdscore.dll`

## pseudocode

```c

```
