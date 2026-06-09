# MdmSettings::GetConnectedAccountsHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012954`
- end: `0x180012ab5`
- name: `?GetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030c0`
- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012954`
- `0x180012d8c`
- `0x18001d4f4`

## string_xrefs

- `0x1800129c2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012a59`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012a09`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012a45`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetConnectedAccountsHash(int a1, _QWORD *a2)
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
          228,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"ConnectedAccountsHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        236,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      230,
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
0x180012954  mov     [rsp+arg_0], rbx
0x180012959  mov     [rsp+arg_10], rsi
0x18001295e  push    rdi
0x18001295f  sub     rsp, 260h
0x180012966  mov     rax, cs:__security_cookie
0x18001296d  xor     rax, rsp
0x180012970  mov     [rsp+268h+var_18], rax
0x180012978  mov     rdi, rdx
0x18001297b  mov     ebx, ecx
0x18001297d  xor     edx, edx; Val
0x18001297f  lea     rcx, [rsp+268h+var_228]; void *
0x180012984  mov     r8d, 208h; Size
0x18001298a  call    memset_0
0x18001298f  mov     [rsp+268h+var_238], 104h
0x180012997  sub     ebx, 1
0x18001299a  jz      short loc_1800129E4
0x18001299c  cmp     ebx, 1
0x18001299f  jz      short loc_1800129DB
0x1800129a1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800129a8  mov     ebx, 80070057h
0x1800129ad  jz      loc_180012A8D
0x1800129b3  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800129ba  mov     r8d, ebx
0x1800129bd  mov     [rsp+268h+var_240], rax
0x1800129c2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800129c9  mov     [rsp+268h+var_248], 1E4h
0x1800129d1  call    McTemplateU0dsqs_EventWriteTransfer
0x1800129d6  jmp     loc_180012A8D
0x1800129db  mov     rsi, 0FFFFFFFF80000002h
0x1800129e2  jmp     short loc_1800129EB
0x1800129e4  mov     rsi, 0FFFFFFFF80000001h
0x1800129eb  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x1800129f0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800129f5  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800129fa  mov     ebx, eax
0x1800129fc  test    eax, eax
0x1800129fe  jns     short loc_180012A1F
0x180012a00  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012a07  jz      short loc_180012A68
0x180012a09  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012a10  mov     [rsp+268h+var_240], rax
0x180012a15  mov     [rsp+268h+var_248], 1E6h
0x180012a1d  jmp     short loc_180012A59
0x180012a1f  mov     r9, rdi
0x180012a22  lea     r8, aConnectedaccou_0; "ConnectedAccountsHash"
0x180012a29  lea     rdx, [rsp+268h+var_228]
0x180012a2e  mov     rcx, rsi
0x180012a31  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012a36  mov     ebx, eax
0x180012a38  test    eax, eax
0x180012a3a  jns     short loc_180012A8D
0x180012a3c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012a43  jz      short loc_180012A68
0x180012a45  lea     rax, aChrMdmregistry_11; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012a4c  mov     [rsp+268h+var_240], rax
0x180012a51  mov     [rsp+268h+var_248], 1ECh
0x180012a59  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012a60  mov     r8d, ebx
0x180012a63  call    McTemplateU0dsqs_EventWriteTransfer
0x180012a68  cmp     ebx, 80070490h
0x180012a6e  jz      short loc_180012A78
0x180012a70  cmp     ebx, 80070002h
0x180012a76  jnz     short loc_180012A8D
0x180012a78  xor     ebx, ebx
0x180012a7a  mov     [rdi+10h], rbx
0x180012a7e  cmp     qword ptr [rdi+18h], 7
0x180012a83  jbe     short loc_180012A88
0x180012a85  mov     rdi, [rdi]
0x180012a88  xor     eax, eax
0x180012a8a  mov     [rdi], ax
0x180012a8d  mov     eax, ebx
0x180012a8f  mov     rcx, [rsp+268h+var_18]
0x180012a97  xor     rcx, rsp; StackCookie
0x180012a9a  call    __security_check_cookie
0x180012a9f  lea     r11, [rsp+268h+var_8]
0x180012aa7  mov     rbx, [r11+10h]
0x180012aab  mov     rsi, [r11+20h]
0x180012aaf  mov     rsp, r11
0x180012ab2  pop     rdi
0x180012ab3  retn
```
