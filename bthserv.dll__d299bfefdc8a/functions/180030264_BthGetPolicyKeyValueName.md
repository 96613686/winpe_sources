# BthGetPolicyKeyValueName

- ea: `0x180030264`
- end: `0x180030322`
- name: `BthGetPolicyKeyValueName`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c7f0`

## callees

- `0x180030264`

## string_xrefs

- `0x180030291`: `PM_LinkSecurityLevel`
- `0x180030312`: `PM_ServicesAllowedList`
- `0x180030302`: `PM_AllowPrepairing`

## pseudocode

```c
const WCHAR *__fastcall BthGetPolicyKeyValueName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const WCHAR *result; // rax

  if ( a1 > 64 )
  {
    switch ( a1 )
    {
      case 128:
        return L"PM_DevicesAllowedList";
      case 256:
        return L"PM_ServicesAllowedList";
      case 512:
        return L"PM_RequireRestrictedMode";
      case 1024:
        return L"PM_AllowPrepairing";
      default:
        result = L"PM_SetMinimumEncryptionKeySize";
        if ( a1 != 2048 )
          return L"Unknown";
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"PM_LocalDeviceName";
  }
  else
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      v2 = v1 - 1;
      if ( v2 )
      {
        v3 = v2 - 2;
        if ( v3 )
        {
          v4 = v3 - 4;
          if ( v4 )
          {
            v5 = v4 - 8;
            if ( v5 )
            {
              if ( v5 == 16 )
                return L"PM_LinkSecurityLevel";
              else
                return L"Unknown";
            }
            else
            {
              return L"PM_AllowOutOfBandPairing";
            }
          }
          else
          {
            return L"PM_AllowAdvertising";
          }
        }
        else
        {
          return L"PM_AllowConnectableMode";
        }
      }
      else
      {
        return L"PM_AllowDiscoverableMode";
      }
    }
    else
    {
      return L"PM_AllowBluetooth";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030264  cmp     ecx, 40h ; '@'
0x180030267  jg      short loc_1800302C9
0x180030269  jz      short loc_1800302C1
0x18003026b  sub     ecx, 1
0x18003026e  jz      short loc_1800302B9
0x180030270  sub     ecx, 1
0x180030273  jz      short loc_1800302B1
0x180030275  sub     ecx, 2
0x180030278  jz      short loc_1800302A9
0x18003027a  sub     ecx, 4
0x18003027d  jz      short loc_1800302A1
0x18003027f  sub     ecx, 8
0x180030282  jz      short loc_180030299
0x180030284  cmp     ecx, 10h
0x180030287  jz      short loc_180030291
0x180030289  lea     rax, aUnknown; "Unknown"
0x180030290  retn
0x180030291  lea     rax, aPmLinksecurity; "PM_LinkSecurityLevel"
0x180030298  retn
0x180030299  lea     rax, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x1800302a0  retn
0x1800302a1  lea     rax, aPmAllowadverti; "PM_AllowAdvertising"
0x1800302a8  retn
0x1800302a9  lea     rax, aPmAllowconnect; "PM_AllowConnectableMode"
0x1800302b0  retn
0x1800302b1  lea     rax, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x1800302b8  retn
0x1800302b9  lea     rax, aPmAllowbluetoo; "PM_AllowBluetooth"
0x1800302c0  retn
0x1800302c1  lea     rax, aPmLocaldevicen; "PM_LocalDeviceName"
0x1800302c8  retn
0x1800302c9  cmp     ecx, 80h
0x1800302cf  jz      short loc_18003031A
0x1800302d1  cmp     ecx, 100h
0x1800302d7  jz      short loc_180030312
0x1800302d9  cmp     ecx, 200h
0x1800302df  jz      short loc_18003030A
0x1800302e1  cmp     ecx, 400h
0x1800302e7  jz      short loc_180030302
0x1800302e9  cmp     ecx, 800h
0x1800302ef  lea     rdx, aUnknown; "Unknown"
0x1800302f6  lea     rax, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x1800302fd  cmovnz  rax, rdx
0x180030301  retn
0x180030302  lea     rax, aPmAllowprepair; "PM_AllowPrepairing"
0x180030309  retn
0x18003030a  lea     rax, aPmRequirerestr; "PM_RequireRestrictedMode"
0x180030311  retn
0x180030312  lea     rax, aPmServicesallo; "PM_ServicesAllowedList"
0x180030319  retn
0x18003031a  lea     rax, aPmDevicesallow; "PM_DevicesAllowedList"
0x180030321  retn
```
