# MdmSettings::SetStorageInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180014214`
- end: `0x18001433e`
- name: `?SetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180014214`
- `0x18001d908`

## string_xrefs

- `0x180014307`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800142b7`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800142f3`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))`

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
0x180014214  mov     [rsp+arg_0], rbx
0x180014219  mov     [rsp+arg_10], rsi
0x18001421e  push    rdi
0x18001421f  sub     rsp, 260h
0x180014226  mov     rax, cs:__security_cookie
0x18001422d  xor     rax, rsp
0x180014230  mov     [rsp+268h+var_18], rax
0x180014238  mov     rsi, rdx
0x18001423b  mov     ebx, ecx
0x18001423d  xor     edx, edx; Val
0x18001423f  lea     rcx, [rsp+268h+var_228]; void *
0x180014244  mov     r8d, 208h; Size
0x18001424a  call    memset_0
0x18001424f  mov     [rsp+268h+var_238], 104h
0x180014257  sub     ebx, 1
0x18001425a  jz      short loc_180014292
0x18001425c  cmp     ebx, 1
0x18001425f  jz      short loc_180014289
0x180014261  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014268  mov     ebx, 80070057h
0x18001426d  jz      loc_180014316
0x180014273  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x18001427a  mov     [rsp+268h+var_240], rax
0x18001427f  mov     [rsp+268h+var_248], 199h
0x180014287  jmp     short loc_180014307
0x180014289  mov     rdi, 0FFFFFFFF80000002h
0x180014290  jmp     short loc_180014299
0x180014292  mov     rdi, 0FFFFFFFF80000001h
0x180014299  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x18001429e  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800142a3  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800142a8  mov     ebx, eax
0x1800142aa  test    eax, eax
0x1800142ac  jns     short loc_1800142CD
0x1800142ae  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800142b5  jz      short loc_180014316
0x1800142b7  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800142be  mov     [rsp+268h+var_240], rax
0x1800142c3  mov     [rsp+268h+var_248], 19Bh
0x1800142cb  jmp     short loc_180014307
0x1800142cd  mov     r9, rsi
0x1800142d0  lea     r8, aStorageinfohas; "StorageInfoHash"
0x1800142d7  lea     rdx, [rsp+268h+var_228]
0x1800142dc  mov     rcx, rdi
0x1800142df  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x1800142e4  mov     ebx, eax
0x1800142e6  test    eax, eax
0x1800142e8  jns     short loc_180014316
0x1800142ea  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800142f1  jz      short loc_180014316
0x1800142f3  lea     rax, aChrMdmregistry_5; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x1800142fa  mov     [rsp+268h+var_240], rax
0x1800142ff  mov     [rsp+268h+var_248], 1A1h
0x180014307  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001430e  mov     r8d, ebx
0x180014311  call    McTemplateU0dsqs_EventWriteTransfer
0x180014316  mov     eax, ebx
0x180014318  mov     rcx, [rsp+268h+var_18]
0x180014320  xor     rcx, rsp; StackCookie
0x180014323  call    __security_check_cookie
0x180014328  lea     r11, [rsp+268h+var_8]
0x180014330  mov     rbx, [r11+10h]
0x180014334  mov     rsi, [r11+20h]
0x180014338  mov     rsp, r11
0x18001433b  pop     rdi
0x18001433c  retn
```
