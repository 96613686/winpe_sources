# MdmSettings::SetDeviceInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001361c`
- end: `0x180013745`
- name: `?SetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x18001361c`
- `0x18001d248`

## string_xrefs

- `0x18001370f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800136bf`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800136fb`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszDeviceInfoHash, pszValue))`

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
0x18001361c  mov     [rsp+arg_0], rbx
0x180013621  mov     [rsp+arg_10], rsi
0x180013626  push    rdi
0x180013627  sub     rsp, 260h
0x18001362e  mov     rax, cs:__security_cookie
0x180013635  xor     rax, rsp
0x180013638  mov     [rsp+268h+var_18], rax
0x180013640  mov     rsi, rdx
0x180013643  mov     ebx, ecx
0x180013645  xor     edx, edx; Val
0x180013647  lea     rcx, [rsp+268h+var_228]; void *
0x18001364c  mov     r8d, 208h; Size
0x180013652  call    memset_0
0x180013657  mov     [rsp+268h+var_238], 104h
0x18001365f  sub     ebx, 1
0x180013662  jz      short loc_18001369A
0x180013664  cmp     ebx, 1
0x180013667  jz      short loc_180013691
0x180013669  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013670  mov     ebx, 80070057h
0x180013675  jz      loc_18001371E
0x18001367b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013682  mov     [rsp+268h+var_240], rax
0x180013687  mov     [rsp+268h+var_248], 131h
0x18001368f  jmp     short loc_18001370F
0x180013691  mov     rdi, 0FFFFFFFF80000002h
0x180013698  jmp     short loc_1800136A1
0x18001369a  mov     rdi, 0FFFFFFFF80000001h
0x1800136a1  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x1800136a6  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800136ab  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800136b0  mov     ebx, eax
0x1800136b2  test    eax, eax
0x1800136b4  jns     short loc_1800136D5
0x1800136b6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800136bd  jz      short loc_18001371E
0x1800136bf  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800136c6  mov     [rsp+268h+var_240], rax
0x1800136cb  mov     [rsp+268h+var_248], 133h
0x1800136d3  jmp     short loc_18001370F
0x1800136d5  mov     r9, rsi
0x1800136d8  lea     r8, aDeviceinfohash; "DeviceInfoHash"
0x1800136df  lea     rdx, [rsp+268h+var_228]
0x1800136e4  mov     rcx, rdi
0x1800136e7  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x1800136ec  mov     ebx, eax
0x1800136ee  test    eax, eax
0x1800136f0  jns     short loc_18001371E
0x1800136f2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800136f9  jz      short loc_18001371E
0x1800136fb  lea     rax, aChrMdmregistry_10; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013702  mov     [rsp+268h+var_240], rax
0x180013707  mov     [rsp+268h+var_248], 139h
0x18001370f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013716  mov     r8d, ebx
0x180013719  call    McTemplateU0dsqs_EventWriteTransfer
0x18001371e  mov     eax, ebx
0x180013720  mov     rcx, [rsp+268h+var_18]
0x180013728  xor     rcx, rsp; StackCookie
0x18001372b  call    __security_check_cookie
0x180013730  lea     r11, [rsp+268h+var_8]
0x180013738  mov     rbx, [r11+10h]
0x18001373c  mov     rsi, [r11+20h]
0x180013740  mov     rsp, r11
0x180013743  pop     rdi
0x180013744  retn
```
