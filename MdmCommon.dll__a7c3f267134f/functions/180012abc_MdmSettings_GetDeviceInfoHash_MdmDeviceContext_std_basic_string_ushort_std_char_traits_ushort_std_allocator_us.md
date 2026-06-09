# MdmSettings::GetDeviceInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012abc`
- end: `0x180012c1d`
- name: `?GetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012abc`
- `0x180012d8c`
- `0x18001d4f4`

## string_xrefs

- `0x180012b2a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012bc1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012b71`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012bad`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))`

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
0x180012abc  mov     [rsp+arg_0], rbx
0x180012ac1  mov     [rsp+arg_10], rsi
0x180012ac6  push    rdi
0x180012ac7  sub     rsp, 260h
0x180012ace  mov     rax, cs:__security_cookie
0x180012ad5  xor     rax, rsp
0x180012ad8  mov     [rsp+268h+var_18], rax
0x180012ae0  mov     rdi, rdx
0x180012ae3  mov     ebx, ecx
0x180012ae5  xor     edx, edx; Val
0x180012ae7  lea     rcx, [rsp+268h+var_228]; void *
0x180012aec  mov     r8d, 208h; Size
0x180012af2  call    memset_0
0x180012af7  mov     [rsp+268h+var_238], 104h
0x180012aff  sub     ebx, 1
0x180012b02  jz      short loc_180012B4C
0x180012b04  cmp     ebx, 1
0x180012b07  jz      short loc_180012B43
0x180012b09  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012b10  mov     ebx, 80070057h
0x180012b15  jz      loc_180012BF5
0x180012b1b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012b22  mov     r8d, ebx
0x180012b25  mov     [rsp+268h+var_240], rax
0x180012b2a  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012b31  mov     [rsp+268h+var_248], 114h
0x180012b39  call    McTemplateU0dsqs_EventWriteTransfer
0x180012b3e  jmp     loc_180012BF5
0x180012b43  mov     rsi, 0FFFFFFFF80000002h
0x180012b4a  jmp     short loc_180012B53
0x180012b4c  mov     rsi, 0FFFFFFFF80000001h
0x180012b53  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012b58  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012b5d  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012b62  mov     ebx, eax
0x180012b64  test    eax, eax
0x180012b66  jns     short loc_180012B87
0x180012b68  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012b6f  jz      short loc_180012BD0
0x180012b71  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012b78  mov     [rsp+268h+var_240], rax
0x180012b7d  mov     [rsp+268h+var_248], 116h
0x180012b85  jmp     short loc_180012BC1
0x180012b87  mov     r9, rdi
0x180012b8a  lea     r8, aDeviceinfohash; "DeviceInfoHash"
0x180012b91  lea     rdx, [rsp+268h+var_228]
0x180012b96  mov     rcx, rsi
0x180012b99  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012b9e  mov     ebx, eax
0x180012ba0  test    eax, eax
0x180012ba2  jns     short loc_180012BF5
0x180012ba4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012bab  jz      short loc_180012BD0
0x180012bad  lea     rax, aChrMdmregistry_14; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012bb4  mov     [rsp+268h+var_240], rax
0x180012bb9  mov     [rsp+268h+var_248], 11Ch
0x180012bc1  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012bc8  mov     r8d, ebx
0x180012bcb  call    McTemplateU0dsqs_EventWriteTransfer
0x180012bd0  cmp     ebx, 80070490h
0x180012bd6  jz      short loc_180012BE0
0x180012bd8  cmp     ebx, 80070002h
0x180012bde  jnz     short loc_180012BF5
0x180012be0  xor     ebx, ebx
0x180012be2  mov     [rdi+10h], rbx
0x180012be6  cmp     qword ptr [rdi+18h], 7
0x180012beb  jbe     short loc_180012BF0
0x180012bed  mov     rdi, [rdi]
0x180012bf0  xor     eax, eax
0x180012bf2  mov     [rdi], ax
0x180012bf5  mov     eax, ebx
0x180012bf7  mov     rcx, [rsp+268h+var_18]
0x180012bff  xor     rcx, rsp; StackCookie
0x180012c02  call    __security_check_cookie
0x180012c07  lea     r11, [rsp+268h+var_8]
0x180012c0f  mov     rbx, [r11+10h]
0x180012c13  mov     rsi, [r11+20h]
0x180012c17  mov     rsp, r11
0x180012c1a  pop     rdi
0x180012c1b  retn
```
