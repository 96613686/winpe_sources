# CWwanManager::SearchProfileHandler(_GUID *,ushort const *,WWAN_PROFILE_INFO *)

- ea: `0x180084074`
- end: `0x180084460`
- name: `?SearchProfileHandler@CWwanManager@@QEAAKPEAU_GUID@@PEBGPEAUWWAN_PROFILE_INFO@@@Z`
- size: `1004`
- prototype: `unsigned int __fastcall(CWwanManager *__hidden this, struct _GUID *, const unsigned __int16 *, struct WWAN_PROFILE_INFO *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800839d0`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x180076c80`
- `0x18007704c`
- `0x1800806e0`
- `0x180084074`
- `0x18009dc14`
- `0x18009dd40`
- `0x18009e6dc`
- `0x1800b6ac0`
- `0x1800c8520`

## import_xrefs

- `WwanPrfl!WwanProfileCleanup` at `0x18008436e`
- `WwanPrfl!WwanProfileCleanup` at `0x1800843f9`
- `WwanPrfl!WwanProfileCleanup` at `0x180084411`
- `WwanPrfl!WwanProfileCleanup` at `0x18008436e`
- `WwanPrfl!WwanProfileCleanup` at `0x1800843f9`
- `WwanPrfl!WwanProfileCleanup` at `0x180084411`
- `WwanPrfl!WwanProfileInit` at `0x180084113`
- `WwanPrfl!WwanProfileInit` at `0x180084120`
- `WwanPrfl!WwanProfileInit` at `0x1800842d8`
- `WwanPrfl!WwanProfileInit` at `0x180084113`
- `WwanPrfl!WwanProfileInit` at `0x180084120`
- `WwanPrfl!WwanProfileInit` at `0x1800842d8`
- `WwanPrfl!WwanProfileDeinit` at `0x18008437b`
- `WwanPrfl!WwanProfileDeinit` at `0x180084404`
- `WwanPrfl!WwanProfileDeinit` at `0x18008441e`
- `WwanPrfl!WwanProfileDeinit` at `0x18008437b`
- `WwanPrfl!WwanProfileDeinit` at `0x180084404`
- `WwanPrfl!WwanProfileDeinit` at `0x18008441e`

## string_xrefs

- `0x180084154`: `WwanPmParseProfileXml call failed [%u] Reason: %d`
- `0x180084346`: `Comparing Profiles: inProfile.name: %ws; tempProfile.name: %ws`
- `0x1800843a8`: ` Found matching profiles: inProfile.name: %ws; tempProfile.name: %ws; inProfile.simIccID: %ws; tempProfile.simIccID: %ws`

## pseudocode

```c

```
