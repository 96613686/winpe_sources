# WlanSyncTaskCommon::IsProfileEligibleForCDSSync(_GUID const &,WCM_WLAN_PROFILE_INFO const &)

- ea: `0x180030f60`
- end: `0x1800310a1`
- name: `?IsProfileEligibleForCDSSync@WlanSyncTaskCommon@@SA_NAEBU_GUID@@AEBUWCM_WLAN_PROFILE_INFO@@@Z`
- size: `321`
- prototype: `bool __fastcall(const struct _GUID *, const struct WCM_WLAN_PROFILE_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d70`
- `0x1800211b0`

## callees

- `0x18001c92c`
- `0x180030f60`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18003105e`
- `wlanapi!WlanFreeMemory` at `0x18003108c`
- `wlanapi!WlanFreeMemory` at `0x18003105e`
- `wlanapi!WlanFreeMemory` at `0x18003108c`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180030fe4`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180030fe4`

## pseudocode

```c

```
