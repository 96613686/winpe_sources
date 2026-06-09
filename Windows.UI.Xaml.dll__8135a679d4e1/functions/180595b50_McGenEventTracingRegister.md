# McGenEventTracingRegister

- ea: `0x180595b50`
- end: `0x180595d5b`
- name: `McGenEventTracingRegister`
- size: `523`
- prototype: `unsigned int __fastcall(const _GUID *ProviderId, void (__fastcall *EnableCallback)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *), void *CallbackContext, unsigned __int64 *RegHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180595b50`
- `0x18076e110`
- `0x18076f0a4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180595bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180595cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180595bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180595cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595bef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595c0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595c27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595bef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595c0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180595c27`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180595d46`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180595d46`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180595bbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180595bbe`

## string_xrefs

- `0x180595be5`: `EventWrite`
- `0x180595bcc`: `advapi32.dll`
- `0x180595ccc`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c

```
