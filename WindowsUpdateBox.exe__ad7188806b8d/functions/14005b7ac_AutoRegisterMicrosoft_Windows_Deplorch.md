# AutoRegisterMicrosoft_Windows_Deplorch

- ea: `0x14005b7ac`
- end: `0x14005b9a8`
- name: `AutoRegisterMicrosoft_Windows_Deplorch`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001330`

## callees

- `0x140002116`
- `0x14005b7ac`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `ADVAPI32!RegisterTraceGuidsW` at `0x14005b97a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x14005b97a`
- `KERNEL32!GetModuleHandleW` at `0x14005b842`
- `KERNEL32!GetModuleHandleW` at `0x14005b865`
- `KERNEL32!GetModuleHandleW` at `0x14005b842`
- `KERNEL32!GetModuleHandleW` at `0x14005b865`
- `KERNEL32!GetProcAddress` at `0x14005b883`
- `KERNEL32!GetProcAddress` at `0x14005b8a5`
- `KERNEL32!GetProcAddress` at `0x14005b8c7`
- `KERNEL32!GetProcAddress` at `0x14005b883`
- `KERNEL32!GetProcAddress` at `0x14005b8a5`
- `KERNEL32!GetProcAddress` at `0x14005b8c7`
- `KERNEL32!GetVersionExW` at `0x14005b805`
- `KERNEL32!GetVersionExW` at `0x14005b805`

## string_xrefs

- `0x14005b83b`: `advapi32.dll`
- `0x14005b85e`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x14005b879`: `EventWrite`

## pseudocode

```c

```
