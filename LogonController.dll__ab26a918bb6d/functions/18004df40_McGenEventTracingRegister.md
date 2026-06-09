# McGenEventTracingRegister

- ea: `0x18004df40`
- end: `0x18004e128`
- name: `McGenEventTracingRegister`
- size: `488`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18004df40`
- `0x18006c000`
- `0x18006cad0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18004dfae`
- `KERNEL32!GetVersionExW` at `0x18004dfae`
- `KERNEL32!GetProcAddress` at `0x18004e016`
- `KERNEL32!GetProcAddress` at `0x18004e032`
- `KERNEL32!GetProcAddress` at `0x18004e04e`
- `KERNEL32!GetProcAddress` at `0x18004e016`
- `KERNEL32!GetProcAddress` at `0x18004e032`
- `KERNEL32!GetProcAddress` at `0x18004e04e`
- `KERNEL32!GetModuleHandleW` at `0x18004dfe5`
- `KERNEL32!GetModuleHandleW` at `0x18004dffe`
- `KERNEL32!GetModuleHandleW` at `0x18004dfe5`
- `KERNEL32!GetModuleHandleW` at `0x18004dffe`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18004e102`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18004e102`

## string_xrefs

- `0x18004dfde`: `advapi32.dll`
- `0x18004dff7`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x18004e00c`: `EventWrite`

## pseudocode

```c

```
