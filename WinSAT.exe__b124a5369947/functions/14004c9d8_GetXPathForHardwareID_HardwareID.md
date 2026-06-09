# GetXPathForHardwareID(HardwareID)

- ea: `0x14004c9d8`
- end: `0x14004ca96`
- name: `?GetXPathForHardwareID@@YAPEBGW4HardwareID@@@Z`
- size: `190`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400200fc`
- `0x14004d550`
- `0x14004d66c`
- `0x14004da24`
- `0x14004db60`
- `0x14004dc2c`
- `0x14004df20`

## callees

- `0x14004c9d8`

## string_xrefs

- `0x14004ca2d`: `SystemConfig/System/MotherBoard`
- `0x14004ca25`: `SystemConfig/Processor/Instance/Signature/Manufacturer`
- `0x14004ca1d`: `SystemConfig/Processor/Instance/Signature/CompactSignature`
- `0x14004ca15`: `SystemConfig/Memory/TotalPhysical/Bytes`
- `0x14004ca0d`: `SystemConfig/Memory/DIMM`
- `0x14004ca05`: `SystemConfig/Disk/SystemDisk/Size`
- `0x14004ca35`: `SystemConfig/Disk/SystemDisk/DiskNum`
- `0x14004ca8e`: `SystemConfig/Graphics/PNPID`
- `0x14004ca86`: `SystemConfig/Graphics/DriverVersion`
- `0x14004ca7e`: `SystemConfig/Graphics/LDDM`
- `0x14004ca6a`: `SystemConfig/Processor/Instance/X64Running`

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
          return &qword_14012B318;
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
                return &qword_14012B318;
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
0x14004c9d8  cmp     ecx, 40h ; '@'
0x14004c9db  jg      short loc_14004CA3D
0x14004c9dd  jz      short loc_14004CA35
0x14004c9df  sub     ecx, 1
0x14004c9e2  jz      short loc_14004CA2D
0x14004c9e4  sub     ecx, 1
0x14004c9e7  jz      short loc_14004CA25
0x14004c9e9  sub     ecx, 2
0x14004c9ec  jz      short loc_14004CA1D
0x14004c9ee  sub     ecx, 4
0x14004c9f1  jz      short loc_14004CA15
0x14004c9f3  sub     ecx, 8
0x14004c9f6  jz      short loc_14004CA0D
0x14004c9f8  cmp     ecx, 10h
0x14004c9fb  jz      short loc_14004CA05
0x14004c9fd  lea     rax, qword_14012B318
0x14004ca04  retn
0x14004ca05  lea     rax, aSystemconfigDi; "SystemConfig/Disk/SystemDisk/Size"
0x14004ca0c  retn
0x14004ca0d  lea     rax, aSystemconfigMe_1; "SystemConfig/Memory/DIMM"
0x14004ca14  retn
0x14004ca15  lea     rax, aSystemconfigMe; "SystemConfig/Memory/TotalPhysical/Bytes"
0x14004ca1c  retn
0x14004ca1d  lea     rax, aSystemconfigPr; "SystemConfig/Processor/Instance/Signatu"...
0x14004ca24  retn
0x14004ca25  lea     rax, aSystemconfigPr_1; "SystemConfig/Processor/Instance/Signatu"...
0x14004ca2c  retn
0x14004ca2d  lea     rax, aSystemconfigSy; "SystemConfig/System/MotherBoard"
0x14004ca34  retn
0x14004ca35  lea     rax, aSystemconfigDi_0; "SystemConfig/Disk/SystemDisk/DiskNum"
0x14004ca3c  retn
0x14004ca3d  cmp     ecx, 80h
0x14004ca43  jz      short loc_14004CA8E
0x14004ca45  cmp     ecx, 100h
0x14004ca4b  jz      short loc_14004CA86
0x14004ca4d  cmp     ecx, 200h
0x14004ca53  jz      short loc_14004CA7E
0x14004ca55  cmp     ecx, 400h
0x14004ca5b  jz      short loc_14004CA76
0x14004ca5d  cmp     ecx, 800h
0x14004ca63  lea     rdx, qword_14012B318
0x14004ca6a  lea     rax, aSystemconfigPr_0; "SystemConfig/Processor/Instance/X64Runn"...
0x14004ca71  cmovnz  rax, rdx
0x14004ca75  retn
0x14004ca76  lea     rax, aPrograminfoWin; "ProgramInfo/WinEIVersion"
0x14004ca7d  retn
0x14004ca7e  lea     rax, aSystemconfigGr; "SystemConfig/Graphics/LDDM"
0x14004ca85  retn
0x14004ca86  lea     rax, aSystemconfigGr_0; "SystemConfig/Graphics/DriverVersion"
0x14004ca8d  retn
0x14004ca8e  lea     rax, aSystemconfigGr_2; "SystemConfig/Graphics/PNPID"
0x14004ca95  retn
```
