# MdmSettings::GetMobileNetworksHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012a24`
- end: `0x180012b84`
- name: `?GetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800040c0`
- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180012a24`
- `0x18001ce60`

## string_xrefs

- `0x180012a92`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012b29`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012ad9`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012b15`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))`

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
0x180012a24  mov     [rsp+arg_0], rbx
0x180012a29  mov     [rsp+arg_10], rsi
0x180012a2e  push    rdi
0x180012a2f  sub     rsp, 260h
0x180012a36  mov     rax, cs:__security_cookie
0x180012a3d  xor     rax, rsp
0x180012a40  mov     [rsp+268h+var_18], rax
0x180012a48  mov     rdi, rdx
0x180012a4b  mov     ebx, ecx
0x180012a4d  xor     edx, edx; Val
0x180012a4f  lea     rcx, [rsp+268h+var_228]; void *
0x180012a54  mov     r8d, 208h; Size
0x180012a5a  call    memset_0
0x180012a5f  mov     [rsp+268h+var_238], 104h
0x180012a67  sub     ebx, 1
0x180012a6a  jz      short loc_180012AB4
0x180012a6c  cmp     ebx, 1
0x180012a6f  jz      short loc_180012AAB
0x180012a71  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012a78  mov     ebx, 80070057h
0x180012a7d  jz      loc_180012B5D
0x180012a83  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012a8a  mov     r8d, ebx
0x180012a8d  mov     [rsp+268h+var_240], rax
0x180012a92  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012a99  mov     [rsp+268h+var_248], 0E0h
0x180012aa1  call    McTemplateU0dsqs_EventWriteTransfer
0x180012aa6  jmp     loc_180012B5D
0x180012aab  mov     rsi, 0FFFFFFFF80000002h
0x180012ab2  jmp     short loc_180012ABB
0x180012ab4  mov     rsi, 0FFFFFFFF80000001h
0x180012abb  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012ac0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012ac5  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012aca  mov     ebx, eax
0x180012acc  test    eax, eax
0x180012ace  jns     short loc_180012AEF
0x180012ad0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012ad7  jz      short loc_180012B38
0x180012ad9  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012ae0  mov     [rsp+268h+var_240], rax
0x180012ae5  mov     [rsp+268h+var_248], 0E2h
0x180012aed  jmp     short loc_180012B29
0x180012aef  mov     r9, rdi
0x180012af2  lea     r8, aMobilenetworks; "MobileNetworksHash"
0x180012af9  lea     rdx, [rsp+268h+var_228]
0x180012afe  mov     rcx, rsi
0x180012b01  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012b06  mov     ebx, eax
0x180012b08  test    eax, eax
0x180012b0a  jns     short loc_180012B5D
0x180012b0c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012b13  jz      short loc_180012B38
0x180012b15  lea     rax, aChrMdmregistry_2; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012b1c  mov     [rsp+268h+var_240], rax
0x180012b21  mov     [rsp+268h+var_248], 0E8h
0x180012b29  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012b30  mov     r8d, ebx
0x180012b33  call    McTemplateU0dsqs_EventWriteTransfer
0x180012b38  cmp     ebx, 80070490h
0x180012b3e  jz      short loc_180012B48
0x180012b40  cmp     ebx, 80070002h
0x180012b46  jnz     short loc_180012B5D
0x180012b48  xor     ebx, ebx
0x180012b4a  mov     [rdi+10h], rbx
0x180012b4e  cmp     qword ptr [rdi+18h], 7
0x180012b53  jbe     short loc_180012B58
0x180012b55  mov     rdi, [rdi]
0x180012b58  xor     eax, eax
0x180012b5a  mov     [rdi], ax
0x180012b5d  mov     eax, ebx
0x180012b5f  mov     rcx, [rsp+268h+var_18]
0x180012b67  xor     rcx, rsp; StackCookie
0x180012b6a  call    __security_check_cookie
0x180012b6f  lea     r11, [rsp+268h+var_8]
0x180012b77  mov     rbx, [r11+10h]
0x180012b7b  mov     rsi, [r11+20h]
0x180012b7f  mov     rsp, r11
0x180012b82  pop     rdi
0x180012b83  retn
```
