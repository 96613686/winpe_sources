# MdmSettings::GetHardwareInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012848`
- end: `0x1800129a8`
- name: `?GetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180012848`
- `0x1800129b0`
- `0x18001ce60`

## string_xrefs

- `0x1800128b6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001294d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800128fd`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012939`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetHardwareInfoHash(int a1, _QWORD *a2)
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
          72,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"HardwareInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        80,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      74,
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
0x180012848  mov     [rsp+arg_0], rbx
0x18001284d  mov     [rsp+arg_10], rsi
0x180012852  push    rdi
0x180012853  sub     rsp, 260h
0x18001285a  mov     rax, cs:__security_cookie
0x180012861  xor     rax, rsp
0x180012864  mov     [rsp+268h+var_18], rax
0x18001286c  mov     rdi, rdx
0x18001286f  mov     ebx, ecx
0x180012871  xor     edx, edx; Val
0x180012873  lea     rcx, [rsp+268h+var_228]; void *
0x180012878  mov     r8d, 208h; Size
0x18001287e  call    memset_0
0x180012883  mov     [rsp+268h+var_238], 104h
0x18001288b  sub     ebx, 1
0x18001288e  jz      short loc_1800128D8
0x180012890  cmp     ebx, 1
0x180012893  jz      short loc_1800128CF
0x180012895  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001289c  mov     ebx, 80070057h
0x1800128a1  jz      loc_180012981
0x1800128a7  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800128ae  mov     r8d, ebx
0x1800128b1  mov     [rsp+268h+var_240], rax
0x1800128b6  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800128bd  mov     [rsp+268h+var_248], 148h
0x1800128c5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800128ca  jmp     loc_180012981
0x1800128cf  mov     rsi, 0FFFFFFFF80000002h
0x1800128d6  jmp     short loc_1800128DF
0x1800128d8  mov     rsi, 0FFFFFFFF80000001h
0x1800128df  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x1800128e4  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800128e9  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800128ee  mov     ebx, eax
0x1800128f0  test    eax, eax
0x1800128f2  jns     short loc_180012913
0x1800128f4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800128fb  jz      short loc_18001295C
0x1800128fd  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012904  mov     [rsp+268h+var_240], rax
0x180012909  mov     [rsp+268h+var_248], 14Ah
0x180012911  jmp     short loc_18001294D
0x180012913  mov     r9, rdi
0x180012916  lea     r8, aHardwareinfoha; "HardwareInfoHash"
0x18001291d  lea     rdx, [rsp+268h+var_228]
0x180012922  mov     rcx, rsi
0x180012925  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001292a  mov     ebx, eax
0x18001292c  test    eax, eax
0x18001292e  jns     short loc_180012981
0x180012930  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012937  jz      short loc_18001295C
0x180012939  lea     rax, aChrMdmregistry_16; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012940  mov     [rsp+268h+var_240], rax
0x180012945  mov     [rsp+268h+var_248], 150h
0x18001294d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012954  mov     r8d, ebx
0x180012957  call    McTemplateU0dsqs_EventWriteTransfer
0x18001295c  cmp     ebx, 80070490h
0x180012962  jz      short loc_18001296C
0x180012964  cmp     ebx, 80070002h
0x18001296a  jnz     short loc_180012981
0x18001296c  xor     ebx, ebx
0x18001296e  mov     [rdi+10h], rbx
0x180012972  cmp     qword ptr [rdi+18h], 7
0x180012977  jbe     short loc_18001297C
0x180012979  mov     rdi, [rdi]
0x18001297c  xor     eax, eax
0x18001297e  mov     [rdi], ax
0x180012981  mov     eax, ebx
0x180012983  mov     rcx, [rsp+268h+var_18]
0x18001298b  xor     rcx, rsp; StackCookie
0x18001298e  call    __security_check_cookie
0x180012993  lea     r11, [rsp+268h+var_8]
0x18001299b  mov     rbx, [r11+10h]
0x18001299f  mov     rsi, [r11+20h]
0x1800129a3  mov     rsp, r11
0x1800129a6  pop     rdi
0x1800129a7  retn
```
