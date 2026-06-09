# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x180010264`
- end: `0x180010427`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `451`
- prototype: `const char *__fastcall(int, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012c04`
- `0x1800176e4`
- `0x180018568`
- `0x18001f27c`
- `0x18001f45c`
- `0x18001f53c`
- `0x18001f898`

## callees

- `0x180010264`
- `0x180029734`

## string_xrefs

- `0x1800103f7`: `SharedAccess`

## pseudocode

```c
const char *__fastcall NetworkingTriageScenario::EnumToString(int a1, __int64 a2)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // rcx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx

  if ( a1 <= 13 )
  {
    if ( a1 == 13 )
      return "WlanMediaManager";
    if ( a1 > 6 )
    {
      v7 = a1 - 7;
      if ( !v7 )
        return "NetworkStatus";
      v8 = v7 - 1;
      if ( !v8 )
        return "NetworkUX";
      v9 = v8 - 1;
      if ( !v9 )
        return "NetworkIcon";
      v10 = v9 - 1;
      if ( !v10 )
        return "WiFiNetworkManager";
      v5 = (unsigned int)(v10 - 1);
      if ( !(_DWORD)v5 )
        return "NetworkSettingHandlers";
      if ( (_DWORD)v5 == 1 )
        return "WiFiWinRTAPIs";
    }
    else
    {
      if ( a1 == 6 )
        return "PNI";
      if ( !a1 )
        return "NetworkListManager";
      v2 = a1 - 1;
      if ( !v2 )
        return "DUSM";
      v3 = v2 - 1;
      if ( !v3 )
        return "NCSI";
      v4 = v3 - 1;
      if ( !v4 )
        return "TcpIp";
      v5 = (unsigned int)(v4 - 1);
      if ( !(_DWORD)v5 )
        return "WindowsConnectionManager";
      if ( (_DWORD)v5 == 1 )
        return "Wwan";
    }
    goto LABEL_51;
  }
  if ( a1 <= 20 )
  {
    if ( a1 == 20 )
      return "EthernetMediaManager";
    v11 = a1 - 14;
    if ( !v11 )
      return "EapRequestHandler";
    v12 = v11 - 1;
    if ( !v12 )
      return "WiFi";
    v13 = v12 - 1;
    if ( !v13 )
      return "Firewall";
    v14 = v13 - 1;
    if ( !v14 )
      return "EapTls";
    v5 = (unsigned int)(v14 - 1);
    if ( !(_DWORD)v5 )
      return "EapHost";
    if ( (_DWORD)v5 == 1 )
      return "Peap";
    goto LABEL_51;
  }
  v15 = a1 - 21;
  if ( !v15 )
    return "Dot3";
  v16 = v15 - 1;
  if ( !v16 )
    return "SettingsApp";
  v17 = v16 - 2;
  if ( !v17 )
    return "EsimPolicyManager";
  v5 = (unsigned int)(v17 - 1);
  if ( !(_DWORD)v5 )
    return "TetheringSvc";
  if ( (_DWORD)v5 != 1 )
  {
LABEL_51:
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, a2);
    return "Unknown";
  }
  return "SharedAccess";
}

```

## disassembly

```asm
0x180010264  sub     rsp, 28h
0x180010268  cmp     ecx, 0Dh
0x18001026b  jg      loc_180010369
0x180010271  jz      loc_18001035D
0x180010277  cmp     ecx, 6
0x18001027a  jg      short loc_1800102F3
0x18001027c  jz      short loc_1800102E7
0x18001027e  test    ecx, ecx
0x180010280  jz      short loc_1800102DB
0x180010282  sub     ecx, 1
0x180010285  jz      short loc_1800102CF
0x180010287  sub     ecx, 1
0x18001028a  jz      short loc_1800102C3
0x18001028c  sub     ecx, 1
0x18001028f  jz      short loc_1800102B7
0x180010291  sub     ecx, 1
0x180010294  jz      short loc_1800102AB
0x180010296  cmp     ecx, 1
0x180010299  jnz     loc_1800103E9
0x18001029f  lea     rax, aWwan; "Wwan"
0x1800102a6  jmp     loc_180010422
0x1800102ab  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x1800102b2  jmp     loc_180010422
0x1800102b7  lea     rax, aTcpip; "TcpIp"
0x1800102be  jmp     loc_180010422
0x1800102c3  lea     rax, aNcsi; "NCSI"
0x1800102ca  jmp     loc_180010422
0x1800102cf  lea     rax, aDusm; "DUSM"
0x1800102d6  jmp     loc_180010422
0x1800102db  lea     rax, aNetworklistman; "NetworkListManager"
0x1800102e2  jmp     loc_180010422
0x1800102e7  lea     rax, aPni; "PNI"
0x1800102ee  jmp     loc_180010422
0x1800102f3  sub     ecx, 7
0x1800102f6  jz      short loc_180010351
0x1800102f8  sub     ecx, 1
0x1800102fb  jz      short loc_180010345
0x1800102fd  sub     ecx, 1
0x180010300  jz      short loc_180010339
0x180010302  sub     ecx, 1
0x180010305  jz      short loc_18001032D
0x180010307  sub     ecx, 1
0x18001030a  jz      short loc_180010321
0x18001030c  cmp     ecx, 1
0x18001030f  jnz     loc_1800103E9
0x180010315  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x18001031c  jmp     loc_180010422
0x180010321  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x180010328  jmp     loc_180010422
0x18001032d  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x180010334  jmp     loc_180010422
0x180010339  lea     rax, aNetworkicon; "NetworkIcon"
0x180010340  jmp     loc_180010422
0x180010345  lea     rax, aNetworkux; "NetworkUX"
0x18001034c  jmp     loc_180010422
0x180010351  lea     rax, aNetworkstatus; "NetworkStatus"
0x180010358  jmp     loc_180010422
0x18001035d  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x180010364  jmp     loc_180010422
0x180010369  cmp     ecx, 14h
0x18001036c  jg      short loc_1800103D0
0x18001036e  jz      short loc_1800103C7
0x180010370  sub     ecx, 0Eh
0x180010373  jz      short loc_1800103BE
0x180010375  sub     ecx, 1
0x180010378  jz      short loc_1800103B5
0x18001037a  sub     ecx, 1
0x18001037d  jz      short loc_1800103AC
0x18001037f  sub     ecx, 1
0x180010382  jz      short loc_1800103A3
0x180010384  sub     ecx, 1
0x180010387  jz      short loc_18001039A
0x180010389  cmp     ecx, 1
0x18001038c  jnz     short loc_1800103E9
0x18001038e  lea     rax, aPeap; "Peap"
0x180010395  jmp     loc_180010422
0x18001039a  lea     rax, aEaphost; "EapHost"
0x1800103a1  jmp     short loc_180010422
0x1800103a3  lea     rax, aEaptls; "EapTls"
0x1800103aa  jmp     short loc_180010422
0x1800103ac  lea     rax, aFirewall; "Firewall"
0x1800103b3  jmp     short loc_180010422
0x1800103b5  lea     rax, aWifi; "WiFi"
0x1800103bc  jmp     short loc_180010422
0x1800103be  lea     rax, aEaprequesthand; "EapRequestHandler"
0x1800103c5  jmp     short loc_180010422
0x1800103c7  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x1800103ce  jmp     short loc_180010422
0x1800103d0  sub     ecx, 15h
0x1800103d3  jz      short loc_18001041B
0x1800103d5  sub     ecx, 1
0x1800103d8  jz      short loc_180010412
0x1800103da  sub     ecx, 2
0x1800103dd  jz      short loc_180010409
0x1800103df  sub     ecx, 1
0x1800103e2  jz      short loc_180010400
0x1800103e4  cmp     ecx, 1
0x1800103e7  jz      short loc_1800103F7
0x1800103e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800103ee  lea     rax, aUnknown; "Unknown"
0x1800103f5  jmp     short loc_180010422
0x1800103f7  lea     rax, aSharedaccess; "SharedAccess"
0x1800103fe  jmp     short loc_180010422
0x180010400  lea     rax, aTetheringsvc; "TetheringSvc"
0x180010407  jmp     short loc_180010422
0x180010409  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x180010410  jmp     short loc_180010422
0x180010412  lea     rax, aSettingsapp; "SettingsApp"
0x180010419  jmp     short loc_180010422
0x18001041b  lea     rax, aDot3; "Dot3"
0x180010422  add     rsp, 28h
0x180010426  retn
```
