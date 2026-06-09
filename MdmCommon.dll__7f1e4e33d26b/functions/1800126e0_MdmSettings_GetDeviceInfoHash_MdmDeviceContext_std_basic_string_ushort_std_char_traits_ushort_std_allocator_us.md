# MdmSettings::GetDeviceInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800126e0`
- end: `0x180012840`
- name: `?GetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800126e0`
- `0x1800129b0`
- `0x18001ce60`

## string_xrefs

- `0x18001274e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800127e5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012795`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800127d1`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetDeviceInfoHash(int a1, _QWORD *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v8; // rsi
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  unsigned int v14[4]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v15, 0, 0x208u);
  v14[0] = 260;
  v6 = a1 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      MdmCommonSettingValuesPersistedLocation = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v5,
          v4,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          20,
          "CBR(hKey != nullptr)",
          *(_QWORD *)v14);
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    }
    v8 = -2147483646;
  }
  else
  {
    v8 = -2147483647;
  }
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v15, v14);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"DeviceInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        28,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      22,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  if ( MdmCommonSettingValuesPersistedLocation == -2147023728 || MdmCommonSettingValuesPersistedLocation == -2147024894 )
  {
    MdmCommonSettingValuesPersistedLocation = 0;
    a2[2] = 0;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    *(_WORD *)a2 = 0;
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800126e0  mov     [rsp+arg_0], rbx
0x1800126e5  mov     [rsp+arg_10], rsi
0x1800126ea  push    rdi
0x1800126eb  sub     rsp, 260h
0x1800126f2  mov     rax, cs:__security_cookie
0x1800126f9  xor     rax, rsp
0x1800126fc  mov     [rsp+268h+var_18], rax
0x180012704  mov     rdi, rdx
0x180012707  mov     ebx, ecx
0x180012709  xor     edx, edx; Val
0x18001270b  lea     rcx, [rsp+268h+var_228]; void *
0x180012710  mov     r8d, 208h; Size
0x180012716  call    memset_0
0x18001271b  mov     [rsp+268h+var_238], 104h
0x180012723  sub     ebx, 1
0x180012726  jz      short loc_180012770
0x180012728  cmp     ebx, 1
0x18001272b  jz      short loc_180012767
0x18001272d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012734  mov     ebx, 80070057h
0x180012739  jz      loc_180012819
0x18001273f  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012746  mov     r8d, ebx
0x180012749  mov     [rsp+268h+var_240], rax
0x18001274e  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012755  mov     [rsp+268h+var_248], 114h
0x18001275d  call    McTemplateU0dsqs_EventWriteTransfer
0x180012762  jmp     loc_180012819
0x180012767  mov     rsi, 0FFFFFFFF80000002h
0x18001276e  jmp     short loc_180012777
0x180012770  mov     rsi, 0FFFFFFFF80000001h
0x180012777  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x18001277c  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012781  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012786  mov     ebx, eax
0x180012788  test    eax, eax
0x18001278a  jns     short loc_1800127AB
0x18001278c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012793  jz      short loc_1800127F4
0x180012795  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x18001279c  mov     [rsp+268h+var_240], rax
0x1800127a1  mov     [rsp+268h+var_248], 116h
0x1800127a9  jmp     short loc_1800127E5
0x1800127ab  mov     r9, rdi
0x1800127ae  lea     r8, aDeviceinfohash; "DeviceInfoHash"
0x1800127b5  lea     rdx, [rsp+268h+var_228]
0x1800127ba  mov     rcx, rsi
0x1800127bd  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x1800127c2  mov     ebx, eax
0x1800127c4  test    eax, eax
0x1800127c6  jns     short loc_180012819
0x1800127c8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800127cf  jz      short loc_1800127F4
0x1800127d1  lea     rax, aChrMdmregistry_14; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x1800127d8  mov     [rsp+268h+var_240], rax
0x1800127dd  mov     [rsp+268h+var_248], 11Ch
0x1800127e5  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800127ec  mov     r8d, ebx
0x1800127ef  call    McTemplateU0dsqs_EventWriteTransfer
0x1800127f4  cmp     ebx, 80070490h
0x1800127fa  jz      short loc_180012804
0x1800127fc  cmp     ebx, 80070002h
0x180012802  jnz     short loc_180012819
0x180012804  xor     ebx, ebx
0x180012806  mov     [rdi+10h], rbx
0x18001280a  cmp     qword ptr [rdi+18h], 7
0x18001280f  jbe     short loc_180012814
0x180012811  mov     rdi, [rdi]
0x180012814  xor     eax, eax
0x180012816  mov     [rdi], ax
0x180012819  mov     eax, ebx
0x18001281b  mov     rcx, [rsp+268h+var_18]
0x180012823  xor     rcx, rsp; StackCookie
0x180012826  call    __security_check_cookie
0x18001282b  lea     r11, [rsp+268h+var_8]
0x180012833  mov     rbx, [r11+10h]
0x180012837  mov     rsi, [r11+20h]
0x18001283b  mov     rsp, r11
0x18001283e  pop     rdi
0x18001283f  retn
```
