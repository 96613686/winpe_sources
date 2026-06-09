# CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)

- ea: `0x14002e088`
- end: `0x14002e1ff`
- name: `?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z`
- size: `375`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ITaskDefinition **, struct ITaskFolder **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140030a54`
- `0x140031bc4`

## callees

- `0x14000715c`
- `0x14002a9ec`
- `0x14002cfbc`
- `0x14002e088`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002e1df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002e1df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002e0b3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002e0b3`

## string_xrefs

- `0x14002e127`: `%windir%\system32\deviceenroller.exe`
- `0x14002e0be`: `CreateTaskForUser`

## pseudocode

```c

```
