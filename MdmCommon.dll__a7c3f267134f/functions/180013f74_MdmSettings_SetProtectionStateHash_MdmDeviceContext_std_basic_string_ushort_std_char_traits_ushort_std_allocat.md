# MdmSettings::SetProtectionStateHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013f74`
- end: `0x18001409e`
- name: `?SetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180013f74`
- `0x18001d908`

## string_xrefs

- `0x180014067`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180014017`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180014053`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetProtectionStateHash(int a1, __int64 *a2)
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
          205,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"ProtectionStateHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        213,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))",
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
      207,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013f74  mov     [rsp+arg_0], rbx
0x180013f79  mov     [rsp+arg_10], rsi
0x180013f7e  push    rdi
0x180013f7f  sub     rsp, 260h
0x180013f86  mov     rax, cs:__security_cookie
0x180013f8d  xor     rax, rsp
0x180013f90  mov     [rsp+268h+var_18], rax
0x180013f98  mov     rsi, rdx
0x180013f9b  mov     ebx, ecx
0x180013f9d  xor     edx, edx; Val
0x180013f9f  lea     rcx, [rsp+268h+var_228]; void *
0x180013fa4  mov     r8d, 208h; Size
0x180013faa  call    memset_0
0x180013faf  mov     [rsp+268h+var_238], 104h
0x180013fb7  sub     ebx, 1
0x180013fba  jz      short loc_180013FF2
0x180013fbc  cmp     ebx, 1
0x180013fbf  jz      short loc_180013FE9
0x180013fc1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013fc8  mov     ebx, 80070057h
0x180013fcd  jz      loc_180014076
0x180013fd3  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013fda  mov     [rsp+268h+var_240], rax
0x180013fdf  mov     [rsp+268h+var_248], 1CDh
0x180013fe7  jmp     short loc_180014067
0x180013fe9  mov     rdi, 0FFFFFFFF80000002h
0x180013ff0  jmp     short loc_180013FF9
0x180013ff2  mov     rdi, 0FFFFFFFF80000001h
0x180013ff9  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013ffe  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014003  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180014008  mov     ebx, eax
0x18001400a  test    eax, eax
0x18001400c  jns     short loc_18001402D
0x18001400e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014015  jz      short loc_180014076
0x180014017  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x18001401e  mov     [rsp+268h+var_240], rax
0x180014023  mov     [rsp+268h+var_248], 1CFh
0x18001402b  jmp     short loc_180014067
0x18001402d  mov     r9, rsi
0x180014030  lea     r8, aProtectionstat; "ProtectionStateHash"
0x180014037  lea     rdx, [rsp+268h+var_228]
0x18001403c  mov     rcx, rdi
0x18001403f  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180014044  mov     ebx, eax
0x180014046  test    eax, eax
0x180014048  jns     short loc_180014076
0x18001404a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014051  jz      short loc_180014076
0x180014053  lea     rax, aChrMdmregistry_7; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x18001405a  mov     [rsp+268h+var_240], rax
0x18001405f  mov     [rsp+268h+var_248], 1D5h
0x180014067  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001406e  mov     r8d, ebx
0x180014071  call    McTemplateU0dsqs_EventWriteTransfer
0x180014076  mov     eax, ebx
0x180014078  mov     rcx, [rsp+268h+var_18]
0x180014080  xor     rcx, rsp; StackCookie
0x180014083  call    __security_check_cookie
0x180014088  lea     r11, [rsp+268h+var_8]
0x180014090  mov     rbx, [r11+10h]
0x180014094  mov     rsi, [r11+20h]
0x180014098  mov     rsp, r11
0x18001409b  pop     rdi
0x18001409c  retn
```
