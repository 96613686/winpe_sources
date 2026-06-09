# CWwanManager::AddInterfaceToList(_GUID const *,PnpDeviceProperties const &)

- ea: `0x180072f68`
- end: `0x18007320c`
- name: `?AddInterfaceToList@CWwanManager@@AEAAKPEBU_GUID@@AEBUPnpDeviceProperties@@@Z`
- size: `676`
- prototype: `unsigned int(CWwanManager *__hidden this, const struct _GUID *, const struct PnpDeviceProperties *)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1800741bc`
- `0x180086f30`

## callees

- `0x180008b00`
- `0x18000ac18`
- `0x180012300`
- `0x180013288`
- `0x180014f1c`
- `0x180015d6c`
- `0x180018abc`
- `0x180070f70`
- `0x180072f68`
- `0x180076810`
- `0x1800769a4`
- `0x180076a20`
- `0x18007d354`
- `0x18007d414`
- `0x18008b7b0`
- `0x18008c82c`
- `0x18009426c`
- `0x1800cd010`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180073170`
- `ntdll!WinSqmIsOptedIn` at `0x180073170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073148`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800731b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800731b1`

## string_xrefs

- `0x1800730cf`: `Failed (already exists)`
- `0x1800730e2`: `interface by GUID already exists`
- `0x18007319b`: `Failed to insert created interface into map [%u]`

## pseudocode

```c

```
