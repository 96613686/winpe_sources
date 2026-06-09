# MdmSettings::SetDeviceInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013a0c`
- end: `0x180013b36`
- name: `?SetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003010`
- `0x180011800`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180013a0c`
- `0x18001d908`

## string_xrefs

- `0x180013aff`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013aaf`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013aeb`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetDeviceInfoHash(int a1, __int64 *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v8; // rdi
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
          49,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"DeviceInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        57,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))",
        *(_QWORD *)v14);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      51,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013a0c  mov     [rsp+arg_0], rbx
0x180013a11  mov     [rsp+arg_10], rsi
0x180013a16  push    rdi
0x180013a17  sub     rsp, 260h
0x180013a1e  mov     rax, cs:__security_cookie
0x180013a25  xor     rax, rsp
0x180013a28  mov     [rsp+268h+var_18], rax
0x180013a30  mov     rsi, rdx
0x180013a33  mov     ebx, ecx
0x180013a35  xor     edx, edx; Val
0x180013a37  lea     rcx, [rsp+268h+var_228]; void *
0x180013a3c  mov     r8d, 208h; Size
0x180013a42  call    memset_0
0x180013a47  mov     [rsp+268h+var_238], 104h
0x180013a4f  sub     ebx, 1
0x180013a52  jz      short loc_180013A8A
0x180013a54  cmp     ebx, 1
0x180013a57  jz      short loc_180013A81
0x180013a59  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013a60  mov     ebx, 80070057h
0x180013a65  jz      loc_180013B0E
0x180013a6b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013a72  mov     [rsp+268h+var_240], rax
0x180013a77  mov     [rsp+268h+var_248], 131h
0x180013a7f  jmp     short loc_180013AFF
0x180013a81  mov     rdi, 0FFFFFFFF80000002h
0x180013a88  jmp     short loc_180013A91
0x180013a8a  mov     rdi, 0FFFFFFFF80000001h
0x180013a91  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013a96  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013a9b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013aa0  mov     ebx, eax
0x180013aa2  test    eax, eax
0x180013aa4  jns     short loc_180013AC5
0x180013aa6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013aad  jz      short loc_180013B0E
0x180013aaf  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013ab6  mov     [rsp+268h+var_240], rax
0x180013abb  mov     [rsp+268h+var_248], 133h
0x180013ac3  jmp     short loc_180013AFF
0x180013ac5  mov     r9, rsi
0x180013ac8  lea     r8, aDeviceinfohash; "DeviceInfoHash"
0x180013acf  lea     rdx, [rsp+268h+var_228]
0x180013ad4  mov     rcx, rdi
0x180013ad7  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180013adc  mov     ebx, eax
0x180013ade  test    eax, eax
0x180013ae0  jns     short loc_180013B0E
0x180013ae2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013ae9  jz      short loc_180013B0E
0x180013aeb  lea     rax, aChrMdmregistry_10; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013af2  mov     [rsp+268h+var_240], rax
0x180013af7  mov     [rsp+268h+var_248], 139h
0x180013aff  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013b06  mov     r8d, ebx
0x180013b09  call    McTemplateU0dsqs_EventWriteTransfer
0x180013b0e  mov     eax, ebx
0x180013b10  mov     rcx, [rsp+268h+var_18]
0x180013b18  xor     rcx, rsp; StackCookie
0x180013b1b  call    __security_check_cookie
0x180013b20  lea     r11, [rsp+268h+var_8]
0x180013b28  mov     rbx, [r11+10h]
0x180013b2c  mov     rsi, [r11+20h]
0x180013b30  mov     rsp, r11
0x180013b33  pop     rdi
0x180013b34  retn
```
