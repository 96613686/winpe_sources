# MdmSettings::SetMobileNetworksHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013c6c`
- end: `0x180013d96`
- name: `?SetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180013c6c`
- `0x18001d908`

## string_xrefs

- `0x180013d5f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013d0f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013d4b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetMobileNetworksHash(int a1, __int64 *a2)
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
          253,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"MobileNetworksHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        5,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))",
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
      255,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013c6c  mov     [rsp+arg_0], rbx
0x180013c71  mov     [rsp+arg_10], rsi
0x180013c76  push    rdi
0x180013c77  sub     rsp, 260h
0x180013c7e  mov     rax, cs:__security_cookie
0x180013c85  xor     rax, rsp
0x180013c88  mov     [rsp+268h+var_18], rax
0x180013c90  mov     rsi, rdx
0x180013c93  mov     ebx, ecx
0x180013c95  xor     edx, edx; Val
0x180013c97  lea     rcx, [rsp+268h+var_228]; void *
0x180013c9c  mov     r8d, 208h; Size
0x180013ca2  call    memset_0
0x180013ca7  mov     [rsp+268h+var_238], 104h
0x180013caf  sub     ebx, 1
0x180013cb2  jz      short loc_180013CEA
0x180013cb4  cmp     ebx, 1
0x180013cb7  jz      short loc_180013CE1
0x180013cb9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013cc0  mov     ebx, 80070057h
0x180013cc5  jz      loc_180013D6E
0x180013ccb  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013cd2  mov     [rsp+268h+var_240], rax
0x180013cd7  mov     [rsp+268h+var_248], 0FDh
0x180013cdf  jmp     short loc_180013D5F
0x180013ce1  mov     rdi, 0FFFFFFFF80000002h
0x180013ce8  jmp     short loc_180013CF1
0x180013cea  mov     rdi, 0FFFFFFFF80000001h
0x180013cf1  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013cf6  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013cfb  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013d00  mov     ebx, eax
0x180013d02  test    eax, eax
0x180013d04  jns     short loc_180013D25
0x180013d06  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013d0d  jz      short loc_180013D6E
0x180013d0f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013d16  mov     [rsp+268h+var_240], rax
0x180013d1b  mov     [rsp+268h+var_248], 0FFh
0x180013d23  jmp     short loc_180013D5F
0x180013d25  mov     r9, rsi
0x180013d28  lea     r8, aMobilenetworks; "MobileNetworksHash"
0x180013d2f  lea     rdx, [rsp+268h+var_228]
0x180013d34  mov     rcx, rdi
0x180013d37  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180013d3c  mov     ebx, eax
0x180013d3e  test    eax, eax
0x180013d40  jns     short loc_180013D6E
0x180013d42  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013d49  jz      short loc_180013D6E
0x180013d4b  lea     rax, aChrMdmregistry_20; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013d52  mov     [rsp+268h+var_240], rax
0x180013d57  mov     [rsp+268h+var_248], 105h
0x180013d5f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013d66  mov     r8d, ebx
0x180013d69  call    McTemplateU0dsqs_EventWriteTransfer
0x180013d6e  mov     eax, ebx
0x180013d70  mov     rcx, [rsp+268h+var_18]
0x180013d78  xor     rcx, rsp; StackCookie
0x180013d7b  call    __security_check_cookie
0x180013d80  lea     r11, [rsp+268h+var_8]
0x180013d88  mov     rbx, [r11+10h]
0x180013d8c  mov     rsi, [r11+20h]
0x180013d90  mov     rsp, r11
0x180013d93  pop     rdi
0x180013d94  retn
```
