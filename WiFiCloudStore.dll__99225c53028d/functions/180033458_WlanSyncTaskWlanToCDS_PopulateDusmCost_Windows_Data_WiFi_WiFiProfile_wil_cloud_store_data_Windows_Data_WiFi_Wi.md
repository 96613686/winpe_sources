# WlanSyncTaskWlanToCDS::PopulateDusmCost<Windows::Data::WiFi::WiFiProfile>(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> &,_DUSM_CONNECTION_COST)

- ea: `0x180033458`
- end: `0x180033473`
- name: `??$PopulateDusmCost@UWiFiProfile@WiFi@Data@Windows@@@WlanSyncTaskWlanToCDS@@CA_NAEAV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@W4_DUSM_CONNECTION_COST@@@Z`
- size: `27`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180016ba4`

## callees

- `0x18002c138`

## string_xrefs

- `0x180033461`: `onecoreuap\net\wlan\cloudstore\provider\lib\WlanSyncTaskWlanToCDS.h`

## pseudocode

```c
void __fastcall __noreturn WlanSyncTaskWlanToCDS::PopulateDusmCost<Windows::Data::WiFi::WiFiProfile>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::_FailFast_Unexpected(
    retaddr,
    (void *)0x36,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\WlanSyncTaskWlanToCDS.h",
    a4);
}

```

## disassembly

```asm
0x180033458  sub     rsp, 28h
0x18003345c  mov     rcx, [rsp+28h]; this
0x180033461  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180033468  mov     edx, 36h ; '6'; void *
0x18003346d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
