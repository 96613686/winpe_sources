# TraceLoggingRegister_EventRegister_2U

- ea: `0x180001008`
- end: `0x18000110e`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `262`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180039e40`
- `0x1800509d0`

## callees

- `0x180001008`
- `0x180001cf0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800010f0`
- `KERNEL32!FreeLibrary` at `0x1800010f0`
- `KERNEL32!GetProcAddress` at `0x1800010cd`
- `KERNEL32!GetProcAddress` at `0x1800010cd`
- `KERNEL32!GetModuleHandleExW` at `0x18000109f`
- `KERNEL32!GetModuleHandleExW` at `0x1800010b7`
- `KERNEL32!GetModuleHandleExW` at `0x18000109f`
- `KERNEL32!GetModuleHandleExW` at `0x1800010b7`
- `ADVAPI32!EventRegister` at `0x180001064`
- `ADVAPI32!EventRegister` at `0x180001064`

## string_xrefs

- `0x18000108a`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800010b0`: `advapi32.dll`

## pseudocode

```c

```
