# MdmSettings::SetHardwareInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180013b3c`
- end: `0x180013c66`
- name: `?SetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180013b3c`
- `0x18001d908`

## string_xrefs

- `0x180013c2f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013bdf`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013c1b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetHardwareInfoHash(int a1, __int64 *a2)
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"HardwareInfoHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        109,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))",
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
      103,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013b3c  mov     [rsp+arg_0], rbx
0x180013b41  mov     [rsp+arg_10], rsi
0x180013b46  push    rdi
0x180013b47  sub     rsp, 260h
0x180013b4e  mov     rax, cs:__security_cookie
0x180013b55  xor     rax, rsp
0x180013b58  mov     [rsp+268h+var_18], rax
0x180013b60  mov     rsi, rdx
0x180013b63  mov     ebx, ecx
0x180013b65  xor     edx, edx; Val
0x180013b67  lea     rcx, [rsp+268h+var_228]; void *
0x180013b6c  mov     r8d, 208h; Size
0x180013b72  call    memset_0
0x180013b77  mov     [rsp+268h+var_238], 104h
0x180013b7f  sub     ebx, 1
0x180013b82  jz      short loc_180013BBA
0x180013b84  cmp     ebx, 1
0x180013b87  jz      short loc_180013BB1
0x180013b89  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013b90  mov     ebx, 80070057h
0x180013b95  jz      loc_180013C3E
0x180013b9b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013ba2  mov     [rsp+268h+var_240], rax
0x180013ba7  mov     [rsp+268h+var_248], 165h
0x180013baf  jmp     short loc_180013C2F
0x180013bb1  mov     rdi, 0FFFFFFFF80000002h
0x180013bb8  jmp     short loc_180013BC1
0x180013bba  mov     rdi, 0FFFFFFFF80000001h
0x180013bc1  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013bc6  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013bcb  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013bd0  mov     ebx, eax
0x180013bd2  test    eax, eax
0x180013bd4  jns     short loc_180013BF5
0x180013bd6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013bdd  jz      short loc_180013C3E
0x180013bdf  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013be6  mov     [rsp+268h+var_240], rax
0x180013beb  mov     [rsp+268h+var_248], 167h
0x180013bf3  jmp     short loc_180013C2F
0x180013bf5  mov     r9, rsi
0x180013bf8  lea     r8, aHardwareinfoha; "HardwareInfoHash"
0x180013bff  lea     rdx, [rsp+268h+var_228]
0x180013c04  mov     rcx, rdi
0x180013c07  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x180013c0c  mov     ebx, eax
0x180013c0e  test    eax, eax
0x180013c10  jns     short loc_180013C3E
0x180013c12  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013c19  jz      short loc_180013C3E
0x180013c1b  lea     rax, aChrMdmregistry_13; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013c22  mov     [rsp+268h+var_240], rax
0x180013c27  mov     [rsp+268h+var_248], 16Dh
0x180013c2f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013c36  mov     r8d, ebx
0x180013c39  call    McTemplateU0dsqs_EventWriteTransfer
0x180013c3e  mov     eax, ebx
0x180013c40  mov     rcx, [rsp+268h+var_18]
0x180013c48  xor     rcx, rsp; StackCookie
0x180013c4b  call    __security_check_cookie
0x180013c50  lea     r11, [rsp+268h+var_8]
0x180013c58  mov     rbx, [r11+10h]
0x180013c5c  mov     rsi, [r11+20h]
0x180013c60  mov     rsp, r11
0x180013c63  pop     rdi
0x180013c64  retn
```
