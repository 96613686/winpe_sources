# MdmSettings::SetHardwareInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001374c`
- end: `0x180013875`
- name: `?SetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(int, __int64)`
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
- `0x18001374c`
- `0x18001d248`

## string_xrefs

- `0x18001383f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800137ef`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x18001382b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetHardwareInfoHash(int a1, __int64 a2)
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
          101,
          (__int64)"CBR(hKey != nullptr)");
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue(v8, v15, L"HardwareInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        109,
        (__int64)"CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      103,
      (__int64)"CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x18001374c  mov     [rsp+arg_0], rbx
0x180013751  mov     [rsp+arg_10], rsi
0x180013756  push    rdi
0x180013757  sub     rsp, 260h
0x18001375e  mov     rax, cs:__security_cookie
0x180013765  xor     rax, rsp
0x180013768  mov     [rsp+268h+var_18], rax
0x180013770  mov     rsi, rdx
0x180013773  mov     ebx, ecx
0x180013775  xor     edx, edx; Val
0x180013777  lea     rcx, [rsp+268h+var_228]; void *
0x18001377c  mov     r8d, 208h; Size
0x180013782  call    memset_0
0x180013787  mov     [rsp+268h+var_238], 104h
0x18001378f  sub     ebx, 1
0x180013792  jz      short loc_1800137CA
0x180013794  cmp     ebx, 1
0x180013797  jz      short loc_1800137C1
0x180013799  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800137a0  mov     ebx, 80070057h
0x1800137a5  jz      loc_18001384E
0x1800137ab  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800137b2  mov     [rsp+268h+var_240], rax
0x1800137b7  mov     [rsp+268h+var_248], 165h
0x1800137bf  jmp     short loc_18001383F
0x1800137c1  mov     rdi, 0FFFFFFFF80000002h
0x1800137c8  jmp     short loc_1800137D1
0x1800137ca  mov     rdi, 0FFFFFFFF80000001h
0x1800137d1  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x1800137d6  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800137db  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800137e0  mov     ebx, eax
0x1800137e2  test    eax, eax
0x1800137e4  jns     short loc_180013805
0x1800137e6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800137ed  jz      short loc_18001384E
0x1800137ef  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800137f6  mov     [rsp+268h+var_240], rax
0x1800137fb  mov     [rsp+268h+var_248], 167h
0x180013803  jmp     short loc_18001383F
0x180013805  mov     r9, rsi
0x180013808  lea     r8, aHardwareinfoha; "HardwareInfoHash"
0x18001380f  lea     rdx, [rsp+268h+var_228]
0x180013814  mov     rcx, rdi
0x180013817  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x18001381c  mov     ebx, eax
0x18001381e  test    eax, eax
0x180013820  jns     short loc_18001384E
0x180013822  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013829  jz      short loc_18001384E
0x18001382b  lea     rax, aChrMdmregistry_13; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013832  mov     [rsp+268h+var_240], rax
0x180013837  mov     [rsp+268h+var_248], 16Dh
0x18001383f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013846  mov     r8d, ebx
0x180013849  call    McTemplateU0dsqs_EventWriteTransfer
0x18001384e  mov     eax, ebx
0x180013850  mov     rcx, [rsp+268h+var_18]
0x180013858  xor     rcx, rsp; StackCookie
0x18001385b  call    __security_check_cookie
0x180013860  lea     r11, [rsp+268h+var_8]
0x180013868  mov     rbx, [r11+10h]
0x18001386c  mov     rsi, [r11+20h]
0x180013870  mov     rsp, r11
0x180013873  pop     rdi
0x180013874  retn
```
