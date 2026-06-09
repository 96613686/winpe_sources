# GetXPathForHardwareID(HardwareID)

- ea: `0x18000867c`
- end: `0x180008746`
- name: `?GetXPathForHardwareID@@YAPEBGW4HardwareID@@@Z`
- size: `202`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b90`
- `0x18002cbd0`
- `0x18002ccd8`
- `0x18002cd94`
- `0x18002ce4c`
- `0x18002ceec`

## callees

- `0x18000867c`

## string_xrefs

- `0x1800086b3`: `SystemConfig/Memory/DIMM`
- `0x180008716`: `SystemConfig/Processor/Instance/X64Running`
- `0x1800086d7`: `SystemConfig/System/MotherBoard`
- `0x1800086ce`: `SystemConfig/Processor/Instance/Signature/Manufacturer`
- `0x1800086c5`: `SystemConfig/Processor/Instance/Signature/CompactSignature`
- `0x1800086bc`: `SystemConfig/Memory/TotalPhysical/Bytes`
- `0x1800086aa`: `SystemConfig/Disk/SystemDisk/Size`
- `0x1800086e0`: `SystemConfig/Disk/SystemDisk/DiskNum`
- `0x18000873e`: `SystemConfig/Graphics/PNPID`
- `0x180008735`: `SystemConfig/Graphics/DriverVersion`
- `0x18000872c`: `SystemConfig/Graphics/LDDM`

## pseudocode

```c
const wchar_t *__fastcall GetXPathForHardwareID(int a1)
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
        return L"SystemConfig/Graphics/PNPID";
      case 256:
        return L"SystemConfig/Graphics/DriverVersion";
      case 512:
        return L"SystemConfig/Graphics/LDDM";
      case 1024:
        return L"ProgramInfo/WinEIVersion";
      default:
        result = L"SystemConfig/Processor/Instance/X64Running";
        if ( a1 != 2048 )
          return &String2;
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"SystemConfig/Disk/SystemDisk/DiskNum";
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
                return L"SystemConfig/Disk/SystemDisk/Size";
              else
                return &String2;
            }
            else
            {
              return L"SystemConfig/Memory/DIMM";
            }
          }
          else
          {
            return L"SystemConfig/Memory/TotalPhysical/Bytes";
          }
        }
        else
        {
          return L"SystemConfig/Processor/Instance/Signature/CompactSignature";
        }
      }
      else
      {
        return L"SystemConfig/Processor/Instance/Signature/Manufacturer";
      }
    }
    else
    {
      return L"SystemConfig/System/MotherBoard";
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000867c  cmp     ecx, 40h ; '@'
0x18000867f  jg      short loc_1800086E9
0x180008681  jz      short loc_1800086E0
0x180008683  sub     ecx, 1
0x180008686  jz      short loc_1800086D7
0x180008688  sub     ecx, 1
0x18000868b  jz      short loc_1800086CE
0x18000868d  sub     ecx, 2
0x180008690  jz      short loc_1800086C5
0x180008692  sub     ecx, 4
0x180008695  jz      short loc_1800086BC
0x180008697  sub     ecx, 8
0x18000869a  jz      short loc_1800086B3
0x18000869c  cmp     ecx, 10h
0x18000869f  jz      short loc_1800086AA
0x1800086a1  lea     rax, String2
0x1800086a8  retn
0x1800086aa  lea     rax, aSystemconfigDi; "SystemConfig/Disk/SystemDisk/Size"
0x1800086b1  retn
0x1800086b3  lea     rax, aSystemconfigMe_0; "SystemConfig/Memory/DIMM"
0x1800086ba  retn
0x1800086bc  lea     rax, aSystemconfigMe; "SystemConfig/Memory/TotalPhysical/Bytes"
0x1800086c3  retn
0x1800086c5  lea     rax, aSystemconfigPr; "SystemConfig/Processor/Instance/Signatu"...
0x1800086cc  retn
0x1800086ce  lea     rax, aSystemconfigPr_1; "SystemConfig/Processor/Instance/Signatu"...
0x1800086d5  retn
0x1800086d7  lea     rax, aSystemconfigSy; "SystemConfig/System/MotherBoard"
0x1800086de  retn
0x1800086e0  lea     rax, aSystemconfigDi_0; "SystemConfig/Disk/SystemDisk/DiskNum"
0x1800086e7  retn
0x1800086e9  cmp     ecx, 80h
0x1800086ef  jz      short loc_18000873E
0x1800086f1  cmp     ecx, 100h
0x1800086f7  jz      short loc_180008735
0x1800086f9  cmp     ecx, 200h
0x1800086ff  jz      short loc_18000872C
0x180008701  cmp     ecx, 400h
0x180008707  jz      short loc_180008723
0x180008709  cmp     ecx, 800h
0x18000870f  lea     rdx, String2
0x180008716  lea     rax, aSystemconfigPr_0; "SystemConfig/Processor/Instance/X64Runn"...
0x18000871d  cmovnz  rax, rdx
0x180008721  retn
0x180008723  lea     rax, aPrograminfoWin; "ProgramInfo/WinEIVersion"
0x18000872a  retn
0x18000872c  lea     rax, aSystemconfigGr; "SystemConfig/Graphics/LDDM"
0x180008733  retn
0x180008735  lea     rax, aSystemconfigGr_0; "SystemConfig/Graphics/DriverVersion"
0x18000873c  retn
0x18000873e  lea     rax, aSystemconfigGr_1; "SystemConfig/Graphics/PNPID"
0x180008745  retn
```
