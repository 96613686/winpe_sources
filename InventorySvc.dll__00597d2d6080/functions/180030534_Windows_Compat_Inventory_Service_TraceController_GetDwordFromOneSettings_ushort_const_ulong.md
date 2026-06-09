# Windows::Compat::Inventory::Service::TraceController::GetDwordFromOneSettings(ushort const *,ulong)

- ea: `0x180030534`
- end: `0x1800305eb`
- name: `?GetDwordFromOneSettings@TraceController@Service@Inventory@Compat@Windows@@CAKPEBGK@Z`
- size: `183`
- prototype: `unsigned int __fastcall(LPCWSTR lpValue, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fd04`
- `0x18003060c`

## callees

- `0x1800152d0`
- `0x180030534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030584`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030584`

## string_xrefs

- `0x180030576`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\InvSvc`
- `0x18003058a`: `Windows::Compat::Inventory::Service::TraceController::GetDwordFromOneSettings`

## pseudocode

```c

```
