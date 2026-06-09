# MdmSettings::SetProtectionStateHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013b74`
- end: `0x180013c9d`
- name: `?SetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180013b74`
- `0x18001d248`

## string_xrefs

- `0x180013c67`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013c17`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013c53`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))`

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
0x180013b74  mov     [rsp+arg_0], rbx
0x180013b79  mov     [rsp+arg_10], rsi
0x180013b7e  push    rdi
0x180013b7f  sub     rsp, 260h
0x180013b86  mov     rax, cs:__security_cookie
0x180013b8d  xor     rax, rsp
0x180013b90  mov     [rsp+268h+var_18], rax
0x180013b98  mov     rsi, rdx
0x180013b9b  mov     ebx, ecx
0x180013b9d  xor     edx, edx; Val
0x180013b9f  lea     rcx, [rsp+268h+var_228]; void *
0x180013ba4  mov     r8d, 208h; Size
0x180013baa  call    memset_0
0x180013baf  mov     [rsp+268h+var_238], 104h
0x180013bb7  sub     ebx, 1
0x180013bba  jz      short loc_180013BF2
0x180013bbc  cmp     ebx, 1
0x180013bbf  jz      short loc_180013BE9
0x180013bc1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013bc8  mov     ebx, 80070057h
0x180013bcd  jz      loc_180013C76
0x180013bd3  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013bda  mov     [rsp+268h+var_240], rax
0x180013bdf  mov     [rsp+268h+var_248], 1CDh
0x180013be7  jmp     short loc_180013C67
0x180013be9  mov     rdi, 0FFFFFFFF80000002h
0x180013bf0  jmp     short loc_180013BF9
0x180013bf2  mov     rdi, 0FFFFFFFF80000001h
0x180013bf9  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013bfe  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013c03  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013c08  mov     ebx, eax
0x180013c0a  test    eax, eax
0x180013c0c  jns     short loc_180013C2D
0x180013c0e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013c15  jz      short loc_180013C76
0x180013c17  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013c1e  mov     [rsp+268h+var_240], rax
0x180013c23  mov     [rsp+268h+var_248], 1CFh
0x180013c2b  jmp     short loc_180013C67
0x180013c2d  mov     r9, rsi
0x180013c30  lea     r8, aProtectionstat; "ProtectionStateHash"
0x180013c37  lea     rdx, [rsp+268h+var_228]
0x180013c3c  mov     rcx, rdi
0x180013c3f  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180013c44  mov     ebx, eax
0x180013c46  test    eax, eax
0x180013c48  jns     short loc_180013C76
0x180013c4a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013c51  jz      short loc_180013C76
0x180013c53  lea     rax, aChrMdmregistry_7; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013c5a  mov     [rsp+268h+var_240], rax
0x180013c5f  mov     [rsp+268h+var_248], 1D5h
0x180013c67  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013c6e  mov     r8d, ebx
0x180013c71  call    McTemplateU0dsqs_EventWriteTransfer
0x180013c76  mov     eax, ebx
0x180013c78  mov     rcx, [rsp+268h+var_18]
0x180013c80  xor     rcx, rsp; StackCookie
0x180013c83  call    __security_check_cookie
0x180013c88  lea     r11, [rsp+268h+var_8]
0x180013c90  mov     rbx, [r11+10h]
0x180013c94  mov     rsi, [r11+20h]
0x180013c98  mov     rsp, r11
0x180013c9b  pop     rdi
0x180013c9c  retn
```
