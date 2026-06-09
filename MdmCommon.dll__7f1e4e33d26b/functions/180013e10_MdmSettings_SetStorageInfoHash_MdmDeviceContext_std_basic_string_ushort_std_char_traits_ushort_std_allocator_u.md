# MdmSettings::SetStorageInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013e10`
- end: `0x180013f39`
- name: `?SetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(int, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003010`
- `0x18001142c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180013e10`
- `0x18001d248`

## string_xrefs

- `0x180013f03`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013eb3`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013eef`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetStorageInfoHash(int a1, __int64 *a2)
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
          153,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"StorageInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        161,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))",
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
      155,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013e10  mov     [rsp+arg_0], rbx
0x180013e15  mov     [rsp+arg_10], rsi
0x180013e1a  push    rdi
0x180013e1b  sub     rsp, 260h
0x180013e22  mov     rax, cs:__security_cookie
0x180013e29  xor     rax, rsp
0x180013e2c  mov     [rsp+268h+var_18], rax
0x180013e34  mov     rsi, rdx
0x180013e37  mov     ebx, ecx
0x180013e39  xor     edx, edx; Val
0x180013e3b  lea     rcx, [rsp+268h+var_228]; void *
0x180013e40  mov     r8d, 208h; Size
0x180013e46  call    memset_0
0x180013e4b  mov     [rsp+268h+var_238], 104h
0x180013e53  sub     ebx, 1
0x180013e56  jz      short loc_180013E8E
0x180013e58  cmp     ebx, 1
0x180013e5b  jz      short loc_180013E85
0x180013e5d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013e64  mov     ebx, 80070057h
0x180013e69  jz      loc_180013F12
0x180013e6f  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013e76  mov     [rsp+268h+var_240], rax
0x180013e7b  mov     [rsp+268h+var_248], 199h
0x180013e83  jmp     short loc_180013F03
0x180013e85  mov     rdi, 0FFFFFFFF80000002h
0x180013e8c  jmp     short loc_180013E95
0x180013e8e  mov     rdi, 0FFFFFFFF80000001h
0x180013e95  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013e9a  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013e9f  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013ea4  mov     ebx, eax
0x180013ea6  test    eax, eax
0x180013ea8  jns     short loc_180013EC9
0x180013eaa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013eb1  jz      short loc_180013F12
0x180013eb3  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013eba  mov     [rsp+268h+var_240], rax
0x180013ebf  mov     [rsp+268h+var_248], 19Bh
0x180013ec7  jmp     short loc_180013F03
0x180013ec9  mov     r9, rsi
0x180013ecc  lea     r8, aStorageinfohas; "StorageInfoHash"
0x180013ed3  lea     rdx, [rsp+268h+var_228]
0x180013ed8  mov     rcx, rdi
0x180013edb  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180013ee0  mov     ebx, eax
0x180013ee2  test    eax, eax
0x180013ee4  jns     short loc_180013F12
0x180013ee6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013eed  jz      short loc_180013F12
0x180013eef  lea     rax, aChrMdmregistry_5; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013ef6  mov     [rsp+268h+var_240], rax
0x180013efb  mov     [rsp+268h+var_248], 1A1h
0x180013f03  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013f0a  mov     r8d, ebx
0x180013f0d  call    McTemplateU0dsqs_EventWriteTransfer
0x180013f12  mov     eax, ebx
0x180013f14  mov     rcx, [rsp+268h+var_18]
0x180013f1c  xor     rcx, rsp; StackCookie
0x180013f1f  call    __security_check_cookie
0x180013f24  lea     r11, [rsp+268h+var_8]
0x180013f2c  mov     rbx, [r11+10h]
0x180013f30  mov     rsi, [r11+20h]
0x180013f34  mov     rsp, r11
0x180013f37  pop     rdi
0x180013f38  retn
```
