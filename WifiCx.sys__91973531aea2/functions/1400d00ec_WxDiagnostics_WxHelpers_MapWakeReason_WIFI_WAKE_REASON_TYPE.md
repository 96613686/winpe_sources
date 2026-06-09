# WxDiagnostics::WxHelpers::MapWakeReason(_WIFI_WAKE_REASON_TYPE)

- ea: `0x1400d00ec`
- end: `0x1400d0148`
- name: `?MapWakeReason@WxHelpers@WxDiagnostics@@YAPEBGW4_WIFI_WAKE_REASON_TYPE@@@Z`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140035fb4`
- `0x1400d7970`
- `0x1400d7b40`

## callees

- `0x1400d00ec`

## string_xrefs

- `0x1400d011c`: `WifiWakeReasonTypeIncomingActionFrame`

## pseudocode

```c
const wchar_t *__fastcall WxDiagnostics::WxHelpers::MapWakeReason(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx

  v1 = a1 - 1;
  if ( !v1 )
    return L"WifiWakeReasonTypeNloDiscovery";
  v2 = v1 - 1;
  if ( !v2 )
    return L"WifiWakeReasonTypeApAssociationlost";
  v3 = v2 - 1;
  if ( !v3 )
    return L"WifiWakeReasonTypeGtkHandshakeError";
  v4 = v3 - 1;
  if ( !v4 )
    return L"WifiWakeReasonTypeFourWayHandshakeRequest";
  v5 = v4 - 1;
  if ( !v5 )
    return L"WifiWakeReasonTypeIncomingActionFrame";
  if ( v5 == 1 )
    return L"WifiWakeReasonTypeClientDriverDiagnostic";
  return L"WifiWakeReasonTypeUnknown";
}

```

## disassembly

```asm
0x1400d00ec  sub     ecx, 1
0x1400d00ef  jz      short loc_1400D0140
0x1400d00f1  sub     ecx, 1
0x1400d00f4  jz      short loc_1400D0137
0x1400d00f6  sub     ecx, 1
0x1400d00f9  jz      short loc_1400D012E
0x1400d00fb  sub     ecx, 1
0x1400d00fe  jz      short loc_1400D0125
0x1400d0100  sub     ecx, 1
0x1400d0103  jz      short loc_1400D011C
0x1400d0105  cmp     ecx, 1
0x1400d0108  jz      short loc_1400D0113
0x1400d010a  lea     rax, aWifiwakereason_2; "WifiWakeReasonTypeUnknown"
0x1400d0111  retn
0x1400d0113  lea     rax, aWifiwakereason_5; "WifiWakeReasonTypeClientDriverDiagnosti"...
0x1400d011a  retn
0x1400d011c  lea     rax, aWifiwakereason_3; "WifiWakeReasonTypeIncomingActionFrame"
0x1400d0123  retn
0x1400d0125  lea     rax, aWifiwakereason_4; "WifiWakeReasonTypeFourWayHandshakeReque"...
0x1400d012c  retn
0x1400d012e  lea     rax, aWifiwakereason_1; "WifiWakeReasonTypeGtkHandshakeError"
0x1400d0135  retn
0x1400d0137  lea     rax, aWifiwakereason; "WifiWakeReasonTypeApAssociationlost"
0x1400d013e  retn
0x1400d0140  lea     rax, aWifiwakereason_0; "WifiWakeReasonTypeNloDiscovery"
0x1400d0147  retn
```
