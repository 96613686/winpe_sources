# CheckRegScanTaskCancelled(void *,REGISTRY_SCAN_FUNC_ARGS *,RegQueItem)

- ea: `0x180024278`
- end: `0x1800242d7`
- name: `?CheckRegScanTaskCancelled@@YAJPEAXPEAUREGISTRY_SCAN_FUNC_ARGS@@URegQueItem@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *, struct REGISTRY_SCAN_FUNC_ARGS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180024938`

## callees

- `0x180024278`
- `0x180024660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024288`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024288`

## pseudocode

```c

```
