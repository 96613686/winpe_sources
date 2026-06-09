# MdmSettings::GetMobileNetworksHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012e08`
- end: `0x180012f69`
- name: `?GetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800040d0`
- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180012e08`
- `0x18001d4f4`

## string_xrefs

- `0x180012e76`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012f0d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012ebd`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012ef9`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetMobileNetworksHash(int a1, _QWORD *a2)
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
          224,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"MobileNetworksHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        232,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      226,
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
0x180012e08  mov     [rsp+arg_0], rbx
0x180012e0d  mov     [rsp+arg_10], rsi
0x180012e12  push    rdi
0x180012e13  sub     rsp, 260h
0x180012e1a  mov     rax, cs:__security_cookie
0x180012e21  xor     rax, rsp
0x180012e24  mov     [rsp+268h+var_18], rax
0x180012e2c  mov     rdi, rdx
0x180012e2f  mov     ebx, ecx
0x180012e31  xor     edx, edx; Val
0x180012e33  lea     rcx, [rsp+268h+var_228]; void *
0x180012e38  mov     r8d, 208h; Size
0x180012e3e  call    memset_0
0x180012e43  mov     [rsp+268h+var_238], 104h
0x180012e4b  sub     ebx, 1
0x180012e4e  jz      short loc_180012E98
0x180012e50  cmp     ebx, 1
0x180012e53  jz      short loc_180012E8F
0x180012e55  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012e5c  mov     ebx, 80070057h
0x180012e61  jz      loc_180012F41
0x180012e67  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012e6e  mov     r8d, ebx
0x180012e71  mov     [rsp+268h+var_240], rax
0x180012e76  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012e7d  mov     [rsp+268h+var_248], 0E0h
0x180012e85  call    McTemplateU0dsqs_EventWriteTransfer
0x180012e8a  jmp     loc_180012F41
0x180012e8f  mov     rsi, 0FFFFFFFF80000002h
0x180012e96  jmp     short loc_180012E9F
0x180012e98  mov     rsi, 0FFFFFFFF80000001h
0x180012e9f  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012ea4  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012ea9  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012eae  mov     ebx, eax
0x180012eb0  test    eax, eax
0x180012eb2  jns     short loc_180012ED3
0x180012eb4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012ebb  jz      short loc_180012F1C
0x180012ebd  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012ec4  mov     [rsp+268h+var_240], rax
0x180012ec9  mov     [rsp+268h+var_248], 0E2h
0x180012ed1  jmp     short loc_180012F0D
0x180012ed3  mov     r9, rdi
0x180012ed6  lea     r8, aMobilenetworks; "MobileNetworksHash"
0x180012edd  lea     rdx, [rsp+268h+var_228]
0x180012ee2  mov     rcx, rsi
0x180012ee5  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012eea  mov     ebx, eax
0x180012eec  test    eax, eax
0x180012eee  jns     short loc_180012F41
0x180012ef0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012ef7  jz      short loc_180012F1C
0x180012ef9  lea     rax, aChrMdmregistry_2; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012f00  mov     [rsp+268h+var_240], rax
0x180012f05  mov     [rsp+268h+var_248], 0E8h
0x180012f0d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012f14  mov     r8d, ebx
0x180012f17  call    McTemplateU0dsqs_EventWriteTransfer
0x180012f1c  cmp     ebx, 80070490h
0x180012f22  jz      short loc_180012F2C
0x180012f24  cmp     ebx, 80070002h
0x180012f2a  jnz     short loc_180012F41
0x180012f2c  xor     ebx, ebx
0x180012f2e  mov     [rdi+10h], rbx
0x180012f32  cmp     qword ptr [rdi+18h], 7
0x180012f37  jbe     short loc_180012F3C
0x180012f39  mov     rdi, [rdi]
0x180012f3c  xor     eax, eax
0x180012f3e  mov     [rdi], ax
0x180012f41  mov     eax, ebx
0x180012f43  mov     rcx, [rsp+268h+var_18]
0x180012f4b  xor     rcx, rsp; StackCookie
0x180012f4e  call    __security_check_cookie
0x180012f53  lea     r11, [rsp+268h+var_8]
0x180012f5b  mov     rbx, [r11+10h]
0x180012f5f  mov     rsi, [r11+20h]
0x180012f63  mov     rsp, r11
0x180012f66  pop     rdi
0x180012f67  retn
```
