# Windows::Registry::GetSubKeyList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140235970`
- end: `0x140235bfc`
- name: `?GetSubKeyList@Registry@Windows@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `652`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x14012d230`
- `0x140186c34`
- `0x14037222c`

## callees

- `0x140040964`
- `0x140043284`
- `0x140045404`
- `0x14004caa8`
- `0x1400b3eb4`
- `0x14018b170`
- `0x1402350d0`
- `0x140235970`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140235aea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140235aea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140235a1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140235a1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140235a6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140235a6d`

## string_xrefs

- `0x140235bd5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x140235bea`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c

```
