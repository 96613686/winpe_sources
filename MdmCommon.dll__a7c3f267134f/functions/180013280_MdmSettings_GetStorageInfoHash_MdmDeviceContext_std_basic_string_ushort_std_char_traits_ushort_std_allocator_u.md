# MdmSettings::GetStorageInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013280`
- end: `0x1800133e1`
- name: `?GetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180013280`
- `0x18001d4f4`

## string_xrefs

- `0x1800132ee`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013385`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013335`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013371`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetStorageInfoHash(int a1, _QWORD *a2)
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
          124,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"StorageInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        132,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      126,
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
0x180013280  mov     [rsp+arg_0], rbx
0x180013285  mov     [rsp+arg_10], rsi
0x18001328a  push    rdi
0x18001328b  sub     rsp, 260h
0x180013292  mov     rax, cs:__security_cookie
0x180013299  xor     rax, rsp
0x18001329c  mov     [rsp+268h+var_18], rax
0x1800132a4  mov     rdi, rdx
0x1800132a7  mov     ebx, ecx
0x1800132a9  xor     edx, edx; Val
0x1800132ab  lea     rcx, [rsp+268h+var_228]; void *
0x1800132b0  mov     r8d, 208h; Size
0x1800132b6  call    memset_0
0x1800132bb  mov     [rsp+268h+var_238], 104h
0x1800132c3  sub     ebx, 1
0x1800132c6  jz      short loc_180013310
0x1800132c8  cmp     ebx, 1
0x1800132cb  jz      short loc_180013307
0x1800132cd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800132d4  mov     ebx, 80070057h
0x1800132d9  jz      loc_1800133B9
0x1800132df  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800132e6  mov     r8d, ebx
0x1800132e9  mov     [rsp+268h+var_240], rax
0x1800132ee  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800132f5  mov     [rsp+268h+var_248], 17Ch
0x1800132fd  call    McTemplateU0dsqs_EventWriteTransfer
0x180013302  jmp     loc_1800133B9
0x180013307  mov     rsi, 0FFFFFFFF80000002h
0x18001330e  jmp     short loc_180013317
0x180013310  mov     rsi, 0FFFFFFFF80000001h
0x180013317  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x18001331c  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013321  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013326  mov     ebx, eax
0x180013328  test    eax, eax
0x18001332a  jns     short loc_18001334B
0x18001332c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013333  jz      short loc_180013394
0x180013335  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x18001333c  mov     [rsp+268h+var_240], rax
0x180013341  mov     [rsp+268h+var_248], 17Eh
0x180013349  jmp     short loc_180013385
0x18001334b  mov     r9, rdi
0x18001334e  lea     r8, aStorageinfohas; "StorageInfoHash"
0x180013355  lea     rdx, [rsp+268h+var_228]
0x18001335a  mov     rcx, rsi
0x18001335d  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180013362  mov     ebx, eax
0x180013364  test    eax, eax
0x180013366  jns     short loc_1800133B9
0x180013368  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001336f  jz      short loc_180013394
0x180013371  lea     rax, aChrMdmregistry_1; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180013378  mov     [rsp+268h+var_240], rax
0x18001337d  mov     [rsp+268h+var_248], 184h
0x180013385  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001338c  mov     r8d, ebx
0x18001338f  call    McTemplateU0dsqs_EventWriteTransfer
0x180013394  cmp     ebx, 80070490h
0x18001339a  jz      short loc_1800133A4
0x18001339c  cmp     ebx, 80070002h
0x1800133a2  jnz     short loc_1800133B9
0x1800133a4  xor     ebx, ebx
0x1800133a6  mov     [rdi+10h], rbx
0x1800133aa  cmp     qword ptr [rdi+18h], 7
0x1800133af  jbe     short loc_1800133B4
0x1800133b1  mov     rdi, [rdi]
0x1800133b4  xor     eax, eax
0x1800133b6  mov     [rdi], ax
0x1800133b9  mov     eax, ebx
0x1800133bb  mov     rcx, [rsp+268h+var_18]
0x1800133c3  xor     rcx, rsp; StackCookie
0x1800133c6  call    __security_check_cookie
0x1800133cb  lea     r11, [rsp+268h+var_8]
0x1800133d3  mov     rbx, [r11+10h]
0x1800133d7  mov     rsi, [r11+20h]
0x1800133db  mov     rsp, r11
0x1800133de  pop     rdi
0x1800133df  retn
```
