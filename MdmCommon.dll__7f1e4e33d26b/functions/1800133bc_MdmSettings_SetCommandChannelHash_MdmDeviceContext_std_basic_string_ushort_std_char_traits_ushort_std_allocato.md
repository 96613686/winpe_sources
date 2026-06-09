# MdmSettings::SetCommandChannelHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800133bc`
- end: `0x1800134e5`
- name: `?SetCommandChannelHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x1800133bc`
- `0x18001d248`

## string_xrefs

- `0x180013478`: `CommandChannelHash`
- `0x1800134af`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001345f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x18001349b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszCommandChannelHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetCommandChannelHash(int a1, __int64 *a2)
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
          201,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"CommandChannelHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        209,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszCommandChannelHash, pszValue))",
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
      203,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800133bc  mov     [rsp+arg_0], rbx
0x1800133c1  mov     [rsp+arg_10], rsi
0x1800133c6  push    rdi
0x1800133c7  sub     rsp, 260h
0x1800133ce  mov     rax, cs:__security_cookie
0x1800133d5  xor     rax, rsp
0x1800133d8  mov     [rsp+268h+var_18], rax
0x1800133e0  mov     rsi, rdx
0x1800133e3  mov     ebx, ecx
0x1800133e5  xor     edx, edx; Val
0x1800133e7  lea     rcx, [rsp+268h+var_228]; void *
0x1800133ec  mov     r8d, 208h; Size
0x1800133f2  call    memset_0
0x1800133f7  mov     [rsp+268h+var_238], 104h
0x1800133ff  sub     ebx, 1
0x180013402  jz      short loc_18001343A
0x180013404  cmp     ebx, 1
0x180013407  jz      short loc_180013431
0x180013409  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013410  mov     ebx, 80070057h
0x180013415  jz      loc_1800134BE
0x18001341b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013422  mov     [rsp+268h+var_240], rax
0x180013427  mov     [rsp+268h+var_248], 0C9h
0x18001342f  jmp     short loc_1800134AF
0x180013431  mov     rdi, 0FFFFFFFF80000002h
0x180013438  jmp     short loc_180013441
0x18001343a  mov     rdi, 0FFFFFFFF80000001h
0x180013441  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013446  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001344b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013450  mov     ebx, eax
0x180013452  test    eax, eax
0x180013454  jns     short loc_180013475
0x180013456  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001345d  jz      short loc_1800134BE
0x18001345f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013466  mov     [rsp+268h+var_240], rax
0x18001346b  mov     [rsp+268h+var_248], 0CBh
0x180013473  jmp     short loc_1800134AF
0x180013475  mov     r9, rsi
0x180013478  lea     r8, aCommandchannel; "CommandChannelHash"
0x18001347f  lea     rdx, [rsp+268h+var_228]
0x180013484  mov     rcx, rdi
0x180013487  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x18001348c  mov     ebx, eax
0x18001348e  test    eax, eax
0x180013490  jns     short loc_1800134BE
0x180013492  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013499  jz      short loc_1800134BE
0x18001349b  lea     rax, aChrMdmregistry_9; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x1800134a2  mov     [rsp+268h+var_240], rax
0x1800134a7  mov     [rsp+268h+var_248], 0D1h
0x1800134af  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800134b6  mov     r8d, ebx
0x1800134b9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800134be  mov     eax, ebx
0x1800134c0  mov     rcx, [rsp+268h+var_18]
0x1800134c8  xor     rcx, rsp; StackCookie
0x1800134cb  call    __security_check_cookie
0x1800134d0  lea     r11, [rsp+268h+var_8]
0x1800134d8  mov     rbx, [r11+10h]
0x1800134dc  mov     rsi, [r11+20h]
0x1800134e0  mov     rsp, r11
0x1800134e3  pop     rdi
0x1800134e4  retn
```
