# WlanSyncTaskWlanToCDS::PopulateProfileXml<Windows::Data::WiFi::WiFiProfileCost>(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost> &,ushort const *,_GUID const &,ushort const *)

- ea: `0x180025c9c`
- end: `0x180025cb7`
- name: `??$PopulateProfileXml@UWiFiProfileCost@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CAXAEAV?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@PEBGAEBU_GUID@@1@Z`
- size: `27`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002547c`

## callees

- `0x18002c138`

## string_xrefs

- `0x180025ca5`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`

## pseudocode

```c
void __fastcall __noreturn WlanSyncTaskWlanToCDS::PopulateProfileXml<Windows::Data::WiFi::WiFiProfileCost>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::_FailFast_Unexpected(
    retaddr,
    (void *)0x2D,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
    a4);
}

```

## disassembly

```asm
0x180025c9c  sub     rsp, 28h
0x180025ca0  mov     rcx, [rsp+28h]; this
0x180025ca5  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180025cac  mov     edx, 2Dh ; '-'; void *
0x180025cb1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
