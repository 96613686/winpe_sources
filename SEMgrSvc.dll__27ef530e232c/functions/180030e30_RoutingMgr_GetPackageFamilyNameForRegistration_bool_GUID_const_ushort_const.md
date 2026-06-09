# RoutingMgr::GetPackageFamilyNameForRegistration(bool,_GUID const &,ushort * const)

- ea: `0x180030e30`
- end: `0x18003100f`
- name: `?GetPackageFamilyNameForRegistration@RoutingMgr@@AEAAJ_NAEBU_GUID@@QEAG@Z`
- size: `479`
- prototype: `int __fastcall(RoutingMgr *this, __int64, const struct _GUID *, unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010d40`
- `0x18002f6c0`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x180013274`
- `0x180014898`
- `0x180030e30`
- `0x18003fbdc`
- `0x18007a0d8`
- `0x18007d3ec`
- `0x18007d804`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030e98`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030e98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f71`

## string_xrefs

- `0x180030e75`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180030fda`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180030ea6`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x180030f39`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`

## pseudocode

```c

```
