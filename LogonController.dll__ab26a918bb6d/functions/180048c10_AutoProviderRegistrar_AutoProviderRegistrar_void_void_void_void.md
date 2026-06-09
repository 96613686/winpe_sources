# AutoProviderRegistrar::AutoProviderRegistrar(void (*)(void),void (*)(void))

- ea: `0x180048c10`
- end: `0x180048e11`
- name: `??0AutoProviderRegistrar@@QEAA@P6AXXZ0@Z`
- size: `513`
- prototype: `AutoProviderRegistrar *__fastcall(AutoProviderRegistrar *__hidden this, void (*)(void), void (*)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180048bf0`

## callees

- `0x180048c10`
- `0x18006c000`
- `0x18006cad0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x180048c77`
- `KERNEL32!GetVersionExW` at `0x180048c77`
- `KERNEL32!GetProcAddress` at `0x180048ca8`
- `KERNEL32!GetProcAddress` at `0x180048cc4`
- `KERNEL32!GetProcAddress` at `0x180048ce0`
- `KERNEL32!GetProcAddress` at `0x180048ca8`
- `KERNEL32!GetProcAddress` at `0x180048cc4`
- `KERNEL32!GetProcAddress` at `0x180048ce0`
- `KERNEL32!GetModuleHandleW` at `0x180048c8c`
- `KERNEL32!GetModuleHandleW` at `0x180048d09`
- `KERNEL32!GetModuleHandleW` at `0x180048c8c`
- `KERNEL32!GetModuleHandleW` at `0x180048d09`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180048e06`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180048e06`

## string_xrefs

- `0x180048c85`: `advapi32.dll`
- `0x180048d02`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x180048c9e`: `EventWrite`

## pseudocode

```c

```
