# SensorGroupId::LoadFromReg(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)

- ea: `0x18000ee30`
- end: `0x18000f1f5`
- name: `?LoadFromReg@SensorGroupId@@SAJPEBG0PEAEKPEAK2@Z`
- size: `965`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, LPCWSTR lpValueName@<rdx>, LPBYTE lpData@<r8>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de78`
- `0x18000e4dc`
- `0x1800300e0`
- `0x1800336d0`

## callees

- `0x180005fa0`
- `0x18000ee30`
- `0x18000f200`
- `0x18000f518`
- `0x180044f30`
- `0x180045900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000efca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f01f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f01f`

## pseudocode

```c
__int64 __fastcall SensorGroupId::LoadFromReg(
        const unsigned __int16 *a1,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        DWORD a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v10; // r8d
  signed int v11; // edi
  LSTATUS v12; // eax
  HKEY v13; // rbx
  LSTATUS v14; // eax
  DWORD v15; // ecx
  LSTATUS v16; // eax
  __int64 v17; // rdx
  bool v18; // sf
  __int64 v19; // rdx
  int v20; // eax
  WCHAR *v21; // rdx
  LSTATUS v22; // eax
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpcbData = a4;
  cbData[0] = 0;
  Type = 0;
  if ( !lpValueName )
  {
    if ( !g_wppLevels )
      return 2147942487LL;
    v17 = 55;
LABEL_43:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
      0,
      -2147024809);
    return 2147942487LL;
  }
  if ( a5 )
  {
    *a5 = 0;
    if ( lpData )
    {
      if ( a4 )
      {
LABEL_7:
        if ( a6 )
          *a6 = 0;
        v23 = 0;
        hKey = 0;
        memset_0(SubKey, 0, 0x208u);
        if ( GetSensorGroupStorePath(a1, SubKey, v10, &v23) < 0 )
          goto LABEL_55;
        v11 = 0;
        v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
        if ( !v12 )
          goto LABEL_11;
        if ( v23 )
        {
LABEL_55:
          if ( a1 )
          {
            v20 = StringCchPrintfW(
                    SubKey,
                    0x104u,
                    L"%s\\%s",
                    L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups",
                    a1);
            v11 = v20;
            if ( v20 < 0 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
                  0,
                  v20);
              goto LABEL_24;
            }
            v21 = SubKey;
          }
          else
          {
            v21 = (WCHAR *)L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups";
          }
          v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0x20119u, &hKey);
          v11 = v22;
          v18 = v22 < 0;
          if ( !v22 )
          {
            v13 = hKey;
LABEL_12:
            v14 = RegQueryValueExW(v13, lpValueName, 0, &Type, 0, cbData);
            v11 = v14;
            if ( v14 )
            {
              if ( v14 > 0 )
                v11 = (unsigned __int16)v14 | 0x80070000;
              if ( v11 < 0 )
                goto LABEL_25;
            }
            else
            {
              v11 = 0;
            }
            v15 = cbData[0];
            *a5 = cbData[0];
            if ( a6 )
              *a6 = Type;
            if ( v15 > lpcbData )
            {
              if ( lpcbData )
                v11 = -1072860816;
              goto LABEL_25;
            }
            v16 = RegQueryValueExW(v13, lpValueName, 0, &Type, lpData, &lpcbData);
            v11 = v16;
            if ( v16 )
            {
              if ( v16 > 0 )
                v11 = (unsigned __int16)v16 | 0x80070000;
              if ( v11 < 0 )
              {
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    58,
                    &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
                    0,
                    v11);
                goto LABEL_25;
              }
            }
            else
            {
              v11 = 0;
            }
            *a5 = lpcbData;
LABEL_25:
            if ( v13 )
              RegCloseKey(v13);
            return (unsigned int)v11;
          }
          if ( v22 > 0 )
          {
            v11 = (unsigned __int16)v22 | 0x80070000;
            v18 = 1;
          }
          if ( !v18 || !g_wppLevels )
          {
LABEL_11:
            v13 = hKey;
            if ( v11 < 0 )
              goto LABEL_25;
            goto LABEL_12;
          }
          v19 = 18;
        }
        else
        {
          if ( v12 <= 0 )
            v11 = v12;
          else
            v11 = (unsigned __int16)v12 | 0x80070000;
          if ( !g_wppLevels )
            goto LABEL_24;
          v19 = 16;
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
LABEL_24:
        v13 = hKey;
        goto LABEL_25;
      }
    }
    else if ( !a4 )
    {
      goto LABEL_7;
    }
    if ( !g_wppLevels )
      return 2147942487LL;
    v17 = 57;
    goto LABEL_43;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, -2147467261);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000ee30  push    rbp
0x18000ee32  push    rbx
0x18000ee33  push    rsi
0x18000ee34  push    r12
0x18000ee36  push    r13
0x18000ee38  push    r14
0x18000ee3a  push    r15
0x18000ee3c  lea     rbp, [rsp-190h]
0x18000ee44  sub     rsp, 290h
0x18000ee4b  mov     rax, cs:__security_cookie
0x18000ee52  xor     rax, rsp
0x18000ee55  mov     [rbp+1C0h+var_50], rax
0x18000ee5c  mov     rsi, [rbp+1C0h+arg_20]
0x18000ee63  xor     r13d, r13d
0x18000ee66  mov     r15, [rbp+1C0h+arg_28]
0x18000ee6d  mov     r14, r8
0x18000ee70  mov     [rsp+2C0h+var_278], r9d
0x18000ee75  mov     r12, rdx
0x18000ee78  mov     [rsp+2C0h+cbData], r13d
0x18000ee7d  mov     rbx, rcx
0x18000ee80  mov     [rsp+2C0h+Type], r13d
0x18000ee85  test    rdx, rdx
0x18000ee88  jnz     short loc_18000EEBE
0x18000ee8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ee91  jnb     loc_18000F123
0x18000ee97  mov     eax, 80070057h
0x18000ee9c  mov     rcx, [rbp+1C0h+var_50]
0x18000eea3  xor     rcx, rsp; StackCookie
0x18000eea6  call    __security_check_cookie
0x18000eeab  add     rsp, 290h
0x18000eeb2  pop     r15
0x18000eeb4  pop     r14
0x18000eeb6  pop     r13
0x18000eeb8  pop     r12
0x18000eeba  pop     rsi
0x18000eebb  pop     rbx
0x18000eebc  pop     rbp
0x18000eebd  retn
0x18000eebe  test    rsi, rsi
0x18000eec1  jz      loc_18000F12A
0x18000eec7  mov     [rsi], r13d
0x18000eeca  test    r14, r14
0x18000eecd  jz      loc_18000F099
0x18000eed3  test    r9d, r9d
0x18000eed6  jz      loc_18000F0A2
0x18000eedc  test    r15, r15
0x18000eedf  jz      short loc_18000EEE4
0x18000eee1  mov     [r15], r13d
0x18000eee4  xor     edx, edx; Val
0x18000eee6  mov     [rsp+2C0h+var_38], rdi
0x18000eeee  mov     r8d, 208h; Size
0x18000eef4  mov     [rsp+2C0h+var_290], r13b
0x18000eef9  lea     rcx, [rsp+2C0h+SubKey]; void *
0x18000eefe  mov     [rsp+2C0h+hKey], r13
0x18000ef03  call    memset_0
0x18000ef08  lea     r9, [rsp+2C0h+var_290]; bool *
0x18000ef0d  mov     rcx, rbx; unsigned __int16 *
0x18000ef10  lea     rdx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x18000ef15  call    ?GetSensorGroupStorePath@@YAJPEBGPEAGKPEA_N@Z; GetSensorGroupStorePath(ushort const *,ushort *,ulong,bool *)
0x18000ef1a  test    eax, eax
0x18000ef1c  js      loc_18000F16B
0x18000ef22  lea     rax, [rsp+2C0h+hKey]
0x18000ef27  mov     r9d, 20119h; samDesired
0x18000ef2d  xor     r8d, r8d; ulOptions
0x18000ef30  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000ef35  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x18000ef3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ef41  mov     edi, r13d
0x18000ef44  call    cs:__imp_RegOpenKeyExW
0x18000ef4a  test    eax, eax
0x18000ef4c  jnz     loc_18000EFE1
0x18000ef52  mov     rbx, [rsp+2C0h+hKey]
0x18000ef57  test    edi, edi
0x18000ef59  js      loc_18000F017
0x18000ef5f  lea     rax, [rsp+2C0h+cbData]
0x18000ef64  xor     r8d, r8d; lpReserved
0x18000ef67  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18000ef6c  lea     r9, [rsp+2C0h+Type]; lpType
0x18000ef71  mov     rdx, r12; lpValueName
0x18000ef74  mov     [rsp+2C0h+phkResult], r13; lpData
0x18000ef79  mov     rcx, rbx; hKey
0x18000ef7c  call    cs:__imp_RegQueryValueExW
0x18000ef82  mov     edi, eax
0x18000ef84  test    eax, eax
0x18000ef86  jnz     loc_18000F03F
0x18000ef8c  mov     edi, r13d
0x18000ef8f  mov     ecx, [rsp+2C0h+cbData]
0x18000ef93  mov     [rsi], ecx
0x18000ef95  test    r15, r15
0x18000ef98  jz      short loc_18000EFA1
0x18000ef9a  mov     eax, [rsp+2C0h+Type]
0x18000ef9e  mov     [r15], eax
0x18000efa1  mov     eax, [rsp+2C0h+var_278]
0x18000efa5  cmp     ecx, eax
0x18000efa7  ja      loc_18000F034
0x18000efad  lea     rax, [rsp+2C0h+var_278]
0x18000efb2  xor     r8d, r8d; lpReserved
0x18000efb5  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18000efba  lea     r9, [rsp+2C0h+Type]; lpType
0x18000efbf  mov     rdx, r12; lpValueName
0x18000efc2  mov     [rsp+2C0h+phkResult], r14; lpData
0x18000efc7  mov     rcx, rbx; hKey
0x18000efca  call    cs:__imp_RegQueryValueExW
0x18000efd0  mov     edi, eax
0x18000efd2  test    eax, eax
0x18000efd4  jnz     short loc_18000F053
0x18000efd6  mov     edi, r13d
0x18000efd9  mov     eax, [rsp+2C0h+var_278]
0x18000efdd  mov     [rsi], eax
0x18000efdf  jmp     short loc_18000F017
0x18000efe1  cmp     [rsp+2C0h+var_290], dil
0x18000efe6  jnz     loc_18000F16B
0x18000efec  test    eax, eax
0x18000efee  jle     loc_18000F087
0x18000eff4  movzx   edi, ax
0x18000eff7  or      edi, 80070000h
0x18000effd  test    edi, edi
0x18000efff  jns     loc_18000EF52
0x18000f005  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f00c  jnb     loc_18000F164
0x18000f012  mov     rbx, [rsp+2C0h+hKey]
0x18000f017  test    rbx, rbx
0x18000f01a  jz      short loc_18000F025
0x18000f01c  mov     rcx, rbx; hKey
0x18000f01f  call    cs:__imp_RegCloseKey
0x18000f025  mov     eax, edi
0x18000f027  mov     rdi, [rsp+2C0h+var_38]
0x18000f02f  jmp     loc_18000EE9C
0x18000f034  test    eax, eax
0x18000f036  jz      short loc_18000F017
0x18000f038  mov     edi, 0C00D7170h
0x18000f03d  jmp     short loc_18000F017
0x18000f03f  jle     short loc_18000F04A
0x18000f041  movzx   edi, ax
0x18000f044  or      edi, 80070000h
0x18000f04a  test    edi, edi
0x18000f04c  js      short loc_18000F017
0x18000f04e  jmp     loc_18000EF8F
0x18000f053  jg      short loc_18000F08E
0x18000f055  test    edi, edi
0x18000f057  jns     short loc_18000EFD9
0x18000f059  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f060  jb      short loc_18000F017
0x18000f062  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f069  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000f070  mov     edx, 3Ah ; ':'
0x18000f075  mov     dword ptr [rsp+2C0h+phkResult], edi
0x18000f079  xor     r9d, r9d
0x18000f07c  mov     rcx, [rcx+10h]
0x18000f080  call    WPP_SF_qD
0x18000f085  jmp     short loc_18000F017
0x18000f087  mov     edi, eax
0x18000f089  jmp     loc_18000EFFD
0x18000f08e  movzx   edi, ax
0x18000f091  or      edi, 80070000h
0x18000f097  jmp     short loc_18000F055
0x18000f099  test    r9d, r9d
0x18000f09c  jz      loc_18000EEDC
0x18000f0a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f0a9  jb      loc_18000EE97
0x18000f0af  mov     edx, 39h ; '9'
0x18000f0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0bb  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000f0c2  xor     r9d, r9d
0x18000f0c5  mov     dword ptr [rsp+2C0h+phkResult], 80070057h
0x18000f0cd  mov     rcx, [rcx+10h]
0x18000f0d1  call    WPP_SF_qD
0x18000f0d6  jmp     loc_18000EE97
0x18000f0db  jle     short loc_18000F0E8
0x18000f0dd  movzx   edi, di
0x18000f0e0  or      edi, 80070000h
0x18000f0e6  test    edi, edi
0x18000f0e8  jns     loc_18000EF52
0x18000f0ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f0f5  jb      loc_18000EF52
0x18000f0fb  mov     edx, 12h
0x18000f100  mov     dword ptr [rsp+2C0h+phkResult], edi
0x18000f104  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f10b  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000f112  xor     r9d, r9d
0x18000f115  mov     rcx, [rcx+10h]
0x18000f119  call    WPP_SF_qD
0x18000f11e  jmp     loc_18000F012
0x18000f123  mov     edx, 37h ; '7'
0x18000f128  jmp     short loc_18000F0B4
0x18000f12a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f131  jb      short loc_18000F15A
0x18000f133  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f13a  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000f141  mov     edx, 38h ; '8'
0x18000f146  mov     dword ptr [rsp+2C0h+phkResult], 80004003h
0x18000f14e  xor     r9d, r9d
0x18000f151  mov     rcx, [rcx+10h]
0x18000f155  call    WPP_SF_qD
0x18000f15a  mov     eax, 80004003h
0x18000f15f  jmp     loc_18000EE9C
0x18000f164  mov     edx, 10h
0x18000f169  jmp     short loc_18000F100
0x18000f16b  test    rbx, rbx
0x18000f16e  jz      short loc_18000F1BA
0x18000f170  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000f177  mov     [rsp+2C0h+phkResult], rbx
0x18000f17c  lea     r8, aSS; "%s\\%s"
0x18000f183  mov     edx, 104h; unsigned __int64
0x18000f188  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x18000f18d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f192  mov     edi, eax
0x18000f194  test    eax, eax
0x18000f196  jns     short loc_18000F1B3
0x18000f198  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f19f  jb      loc_18000F012
0x18000f1a5  mov     edx, 11h
0x18000f1aa  mov     dword ptr [rsp+2C0h+phkResult], eax
0x18000f1ae  jmp     loc_18000F104
0x18000f1b3  lea     rdx, [rsp+2C0h+SubKey]
0x18000f1b8  jmp     short loc_18000F1C1
0x18000f1ba  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000f1c1  lea     rax, [rsp+2C0h+hKey]
0x18000f1c6  mov     r9d, 20119h; samDesired
0x18000f1cc  xor     r8d, r8d; ulOptions
0x18000f1cf  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000f1d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f1db  call    cs:__imp_RegOpenKeyExW
0x18000f1e1  mov     edi, eax
0x18000f1e3  test    eax, eax
0x18000f1e5  jnz     loc_18000F0DB
0x18000f1eb  mov     rbx, [rsp+2C0h+hKey]
0x18000f1f0  jmp     loc_18000EF5F
```
