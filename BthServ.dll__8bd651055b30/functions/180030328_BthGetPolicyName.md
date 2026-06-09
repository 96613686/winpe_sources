# BthGetPolicyName

- ea: `0x180030328`
- end: `0x1800303e6`
- name: `BthGetPolicyName`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c7f0`
- `0x180030a44`

## callees

- `0x180030328`

## string_xrefs

- `0x180030355`: `LinkSecurityLevel`
- `0x1800303d6`: `ServicesAllowedList`
- `0x1800303c6`: `AllowPrepairing`

## pseudocode

```c
const wchar_t *__fastcall BthGetPolicyName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const wchar_t *result; // rax

  if ( a1 > 64 )
  {
    switch ( a1 )
    {
      case 128:
        return L"DevicesAllowedList";
      case 256:
        return L"ServicesAllowedList";
      case 512:
        return L"RequireRestrictedMode";
      case 1024:
        return L"AllowPrepairing";
      default:
        result = L"SetMinimumEncryptionKeySize";
        if ( a1 != 2048 )
          return L"Unknown";
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"LocalDeviceName";
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
                return L"LinkSecurityLevel";
              else
                return L"Unknown";
            }
            else
            {
              return L"AllowOutOfBandPairing";
            }
          }
          else
          {
            return L"AllowAdvertising";
          }
        }
        else
        {
          return L"AllowConnectableMode";
        }
      }
      else
      {
        return L"AllowDiscoverableMode";
      }
    }
    else
    {
      return L"AllowBluetooth";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030328  cmp     ecx, 40h ; '@'
0x18003032b  jg      short loc_18003038D
0x18003032d  jz      short loc_180030385
0x18003032f  sub     ecx, 1
0x180030332  jz      short loc_18003037D
0x180030334  sub     ecx, 1
0x180030337  jz      short loc_180030375
0x180030339  sub     ecx, 2
0x18003033c  jz      short loc_18003036D
0x18003033e  sub     ecx, 4
0x180030341  jz      short loc_180030365
0x180030343  sub     ecx, 8
0x180030346  jz      short loc_18003035D
0x180030348  cmp     ecx, 10h
0x18003034b  jz      short loc_180030355
0x18003034d  lea     rax, aUnknown; "Unknown"
0x180030354  retn
0x180030355  lea     rax, aLinksecurityle; "LinkSecurityLevel"
0x18003035c  retn
0x18003035d  lea     rax, aAllowoutofband; "AllowOutOfBandPairing"
0x180030364  retn
0x180030365  lea     rax, aAllowadvertisi; "AllowAdvertising"
0x18003036c  retn
0x18003036d  lea     rax, aAllowconnectab; "AllowConnectableMode"
0x180030374  retn
0x180030375  lea     rax, aAllowdiscovera; "AllowDiscoverableMode"
0x18003037c  retn
0x18003037d  lea     rax, aAllowbluetooth; "AllowBluetooth"
0x180030384  retn
0x180030385  lea     rax, aLocaldevicenam; "LocalDeviceName"
0x18003038c  retn
0x18003038d  cmp     ecx, 80h
0x180030393  jz      short loc_1800303DE
0x180030395  cmp     ecx, 100h
0x18003039b  jz      short loc_1800303D6
0x18003039d  cmp     ecx, 200h
0x1800303a3  jz      short loc_1800303CE
0x1800303a5  cmp     ecx, 400h
0x1800303ab  jz      short loc_1800303C6
0x1800303ad  cmp     ecx, 800h
0x1800303b3  lea     rdx, aUnknown; "Unknown"
0x1800303ba  lea     rax, aSetminimumencr; "SetMinimumEncryptionKeySize"
0x1800303c1  cmovnz  rax, rdx
0x1800303c5  retn
0x1800303c6  lea     rax, aAllowprepairin; "AllowPrepairing"
0x1800303cd  retn
0x1800303ce  lea     rax, aRequirerestric; "RequireRestrictedMode"
0x1800303d5  retn
0x1800303d6  lea     rax, aServicesallowe; "ServicesAllowedList"
0x1800303dd  retn
0x1800303de  lea     rax, aDevicesallowed; "DevicesAllowedList"
0x1800303e5  retn
```
