# NgcHandler::RemovePrebootProtector(void *,_GUID const &)

- ea: `0x18004abdc`
- end: `0x18004ad4d`
- name: `?RemovePrebootProtector@NgcHandler@@QEAAJPEAXAEBU_GUID@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c4d8`

## callees

- `0x1800134a0`
- `0x180014350`
- `0x180018194`
- `0x18004abdc`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004acf4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004ad31`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004acf4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004ad31`

## pseudocode

```c

```
