# NgcHandler::AuthenticateGesture(void *,_GUID const &,_NGC_RPC_GESTURE_INFO const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18000d8bc`
- end: `0x18000e069`
- name: `?AuthenticateGesture@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBU_NGC_RPC_GESTURE_INFO@@PEA_K3@Z`
- size: `1965`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const struct _NGC_RPC_GESTURE_INFO *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d85c`

## callees

- `0x18000b180`
- `0x18000d8bc`
- `0x180012190`
- `0x1800134a0`
- `0x180014350`
- `0x1800143c0`
- `0x180017280`
- `0x180018194`
- `0x1800187b4`
- `0x180018818`
- `0x18001f5c8`
- `0x1800204c4`
- `0x180023278`
- `0x180026bd4`
- `0x18002c640`
- `0x18003cdfc`
- `0x18003d448`
- `0x18003d4a0`
- `0x180047e98`
- `0x180055034`
- `0x18005addc`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e025`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e025`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ddb4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dd1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ddb4`

## string_xrefs

- `0x18000d97f`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c

```
