# IsWdsLoggerSetup(HINSTANCE__ * *)

- ea: `0x180047a34`
- end: `0x180047b1e`
- name: `?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z`
- size: `234`
- prototype: `bool __fastcall(HINSTANCE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800492e0`
- `0x18007ba20`

## callees

- `0x180020dc0`
- `0x18002d2b0`
- `0x180042bac`
- `0x180047a34`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180047a73`
- `KERNEL32!GetModuleHandleExW` at `0x180047a73`
- `KERNEL32!GetProcAddress` at `0x180047a8f`
- `KERNEL32!GetProcAddress` at `0x180047aaa`
- `KERNEL32!GetProcAddress` at `0x180047a8f`
- `KERNEL32!GetProcAddress` at `0x180047aaa`

## string_xrefs

- `0x180047a6a`: `wdscore.dll`

## pseudocode

```c

```
