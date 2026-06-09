# MdmSettings::SetConnectedAccountsHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800134ec`
- end: `0x180013615`
- name: `?SetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x1800134ec`
- `0x18001d248`

## string_xrefs

- `0x1800135df`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001358f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800135cb`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))`

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
0x1800134ec  mov     [rsp+arg_0], rbx
0x1800134f1  mov     [rsp+arg_10], rsi
0x1800134f6  push    rdi
0x1800134f7  sub     rsp, 260h
0x1800134fe  mov     rax, cs:__security_cookie
0x180013505  xor     rax, rsp
0x180013508  mov     [rsp+268h+var_18], rax
0x180013510  mov     rsi, rdx
0x180013513  mov     ebx, ecx
0x180013515  xor     edx, edx; Val
0x180013517  lea     rcx, [rsp+268h+var_228]; void *
0x18001351c  mov     r8d, 208h; Size
0x180013522  call    memset_0
0x180013527  mov     [rsp+268h+var_238], 104h
0x18001352f  sub     ebx, 1
0x180013532  jz      short loc_18001356A
0x180013534  cmp     ebx, 1
0x180013537  jz      short loc_180013561
0x180013539  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013540  mov     ebx, 80070057h
0x180013545  jz      loc_1800135EE
0x18001354b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013552  mov     [rsp+268h+var_240], rax
0x180013557  mov     [rsp+268h+var_248], 201h
0x18001355f  jmp     short loc_1800135DF
0x180013561  mov     rdi, 0FFFFFFFF80000002h
0x180013568  jmp     short loc_180013571
0x18001356a  mov     rdi, 0FFFFFFFF80000001h
0x180013571  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013576  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001357b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013580  mov     ebx, eax
0x180013582  test    eax, eax
0x180013584  jns     short loc_1800135A5
0x180013586  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001358d  jz      short loc_1800135EE
0x18001358f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013596  mov     [rsp+268h+var_240], rax
0x18001359b  mov     [rsp+268h+var_248], 203h
0x1800135a3  jmp     short loc_1800135DF
0x1800135a5  mov     r9, rsi
0x1800135a8  lea     r8, aConnectedaccou_0; "ConnectedAccountsHash"
0x1800135af  lea     rdx, [rsp+268h+var_228]
0x1800135b4  mov     rcx, rdi
0x1800135b7  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x1800135bc  mov     ebx, eax
0x1800135be  test    eax, eax
0x1800135c0  jns     short loc_1800135EE
0x1800135c2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800135c9  jz      short loc_1800135EE
0x1800135cb  lea     rax, aChrMdmregistry_19; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x1800135d2  mov     [rsp+268h+var_240], rax
0x1800135d7  mov     [rsp+268h+var_248], 209h
0x1800135df  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800135e6  mov     r8d, ebx
0x1800135e9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800135ee  mov     eax, ebx
0x1800135f0  mov     rcx, [rsp+268h+var_18]
0x1800135f8  xor     rcx, rsp; StackCookie
0x1800135fb  call    __security_check_cookie
0x180013600  lea     r11, [rsp+268h+var_8]
0x180013608  mov     rbx, [r11+10h]
0x18001360c  mov     rsi, [r11+20h]
0x180013610  mov     rsp, r11
0x180013613  pop     rdi
0x180013614  retn
```
