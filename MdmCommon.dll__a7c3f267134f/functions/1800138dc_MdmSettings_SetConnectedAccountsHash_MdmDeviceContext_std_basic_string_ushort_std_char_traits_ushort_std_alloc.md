# MdmSettings::SetConnectedAccountsHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800138dc`
- end: `0x180013a06`
- name: `?SetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x1800138dc`
- `0x18001d908`

## string_xrefs

- `0x1800139cf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001397f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800139bb`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetConnectedAccountsHash(int a1, __int64 *a2)
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
          1,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"ConnectedAccountsHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        9,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))",
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
      3,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800138dc  mov     [rsp+arg_0], rbx
0x1800138e1  mov     [rsp+arg_10], rsi
0x1800138e6  push    rdi
0x1800138e7  sub     rsp, 260h
0x1800138ee  mov     rax, cs:__security_cookie
0x1800138f5  xor     rax, rsp
0x1800138f8  mov     [rsp+268h+var_18], rax
0x180013900  mov     rsi, rdx
0x180013903  mov     ebx, ecx
0x180013905  xor     edx, edx; Val
0x180013907  lea     rcx, [rsp+268h+var_228]; void *
0x18001390c  mov     r8d, 208h; Size
0x180013912  call    memset_0
0x180013917  mov     [rsp+268h+var_238], 104h
0x18001391f  sub     ebx, 1
0x180013922  jz      short loc_18001395A
0x180013924  cmp     ebx, 1
0x180013927  jz      short loc_180013951
0x180013929  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013930  mov     ebx, 80070057h
0x180013935  jz      loc_1800139DE
0x18001393b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013942  mov     [rsp+268h+var_240], rax
0x180013947  mov     [rsp+268h+var_248], 201h
0x18001394f  jmp     short loc_1800139CF
0x180013951  mov     rdi, 0FFFFFFFF80000002h
0x180013958  jmp     short loc_180013961
0x18001395a  mov     rdi, 0FFFFFFFF80000001h
0x180013961  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013966  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001396b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013970  mov     ebx, eax
0x180013972  test    eax, eax
0x180013974  jns     short loc_180013995
0x180013976  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001397d  jz      short loc_1800139DE
0x18001397f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013986  mov     [rsp+268h+var_240], rax
0x18001398b  mov     [rsp+268h+var_248], 203h
0x180013993  jmp     short loc_1800139CF
0x180013995  mov     r9, rsi
0x180013998  lea     r8, aConnectedaccou_0; "ConnectedAccountsHash"
0x18001399f  lea     rdx, [rsp+268h+var_228]
0x1800139a4  mov     rcx, rdi
0x1800139a7  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x1800139ac  mov     ebx, eax
0x1800139ae  test    eax, eax
0x1800139b0  jns     short loc_1800139DE
0x1800139b2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800139b9  jz      short loc_1800139DE
0x1800139bb  lea     rax, aChrMdmregistry_19; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x1800139c2  mov     [rsp+268h+var_240], rax
0x1800139c7  mov     [rsp+268h+var_248], 209h
0x1800139cf  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800139d6  mov     r8d, ebx
0x1800139d9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800139de  mov     eax, ebx
0x1800139e0  mov     rcx, [rsp+268h+var_18]
0x1800139e8  xor     rcx, rsp; StackCookie
0x1800139eb  call    __security_check_cookie
0x1800139f0  lea     r11, [rsp+268h+var_8]
0x1800139f8  mov     rbx, [r11+10h]
0x1800139fc  mov     rsi, [r11+20h]
0x180013a00  mov     rsp, r11
0x180013a03  pop     rdi
0x180013a04  retn
```
