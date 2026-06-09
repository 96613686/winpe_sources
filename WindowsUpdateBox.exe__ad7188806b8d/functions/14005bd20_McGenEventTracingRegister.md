# McGenEventTracingRegister

- ea: `0x14005bd20`
- end: `0x14005bf33`
- name: `McGenEventTracingRegister`
- size: `531`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002116`
- `0x14005bd20`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `ADVAPI32!RegisterTraceGuidsW` at `0x14005bf00`
- `ADVAPI32!RegisterTraceGuidsW` at `0x14005bf00`
- `KERNEL32!GetModuleHandleW` at `0x14005bdd0`
- `KERNEL32!GetModuleHandleW` at `0x14005bdf3`
- `KERNEL32!GetModuleHandleW` at `0x14005bdd0`
- `KERNEL32!GetModuleHandleW` at `0x14005bdf3`
- `KERNEL32!GetProcAddress` at `0x14005be11`
- `KERNEL32!GetProcAddress` at `0x14005be33`
- `KERNEL32!GetProcAddress` at `0x14005be55`
- `KERNEL32!GetProcAddress` at `0x14005be11`
- `KERNEL32!GetProcAddress` at `0x14005be33`
- `KERNEL32!GetProcAddress` at `0x14005be55`
- `KERNEL32!GetVersionExW` at `0x14005bd93`
- `KERNEL32!GetVersionExW` at `0x14005bd93`

## string_xrefs

- `0x14005bdc9`: `advapi32.dll`
- `0x14005bdec`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x14005be07`: `EventWrite`

## pseudocode

```c

```
