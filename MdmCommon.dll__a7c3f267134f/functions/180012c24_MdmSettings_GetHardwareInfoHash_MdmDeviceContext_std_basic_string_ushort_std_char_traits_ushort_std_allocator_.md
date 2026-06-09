# MdmSettings::GetHardwareInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012c24`
- end: `0x180012d85`
- name: `?GetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x180012c24`
- `0x180012d8c`
- `0x18001d4f4`

## string_xrefs

- `0x180012c92`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012d29`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012cd9`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012d15`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszHardwareInfoHash, pszValue))`

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
0x180012c24  mov     [rsp+arg_0], rbx
0x180012c29  mov     [rsp+arg_10], rsi
0x180012c2e  push    rdi
0x180012c2f  sub     rsp, 260h
0x180012c36  mov     rax, cs:__security_cookie
0x180012c3d  xor     rax, rsp
0x180012c40  mov     [rsp+268h+var_18], rax
0x180012c48  mov     rdi, rdx
0x180012c4b  mov     ebx, ecx
0x180012c4d  xor     edx, edx; Val
0x180012c4f  lea     rcx, [rsp+268h+var_228]; void *
0x180012c54  mov     r8d, 208h; Size
0x180012c5a  call    memset_0
0x180012c5f  mov     [rsp+268h+var_238], 104h
0x180012c67  sub     ebx, 1
0x180012c6a  jz      short loc_180012CB4
0x180012c6c  cmp     ebx, 1
0x180012c6f  jz      short loc_180012CAB
0x180012c71  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012c78  mov     ebx, 80070057h
0x180012c7d  jz      loc_180012D5D
0x180012c83  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012c8a  mov     r8d, ebx
0x180012c8d  mov     [rsp+268h+var_240], rax
0x180012c92  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012c99  mov     [rsp+268h+var_248], 148h
0x180012ca1  call    McTemplateU0dsqs_EventWriteTransfer
0x180012ca6  jmp     loc_180012D5D
0x180012cab  mov     rsi, 0FFFFFFFF80000002h
0x180012cb2  jmp     short loc_180012CBB
0x180012cb4  mov     rsi, 0FFFFFFFF80000001h
0x180012cbb  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012cc0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012cc5  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012cca  mov     ebx, eax
0x180012ccc  test    eax, eax
0x180012cce  jns     short loc_180012CEF
0x180012cd0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012cd7  jz      short loc_180012D38
0x180012cd9  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012ce0  mov     [rsp+268h+var_240], rax
0x180012ce5  mov     [rsp+268h+var_248], 14Ah
0x180012ced  jmp     short loc_180012D29
0x180012cef  mov     r9, rdi
0x180012cf2  lea     r8, aHardwareinfoha; "HardwareInfoHash"
0x180012cf9  lea     rdx, [rsp+268h+var_228]
0x180012cfe  mov     rcx, rsi
0x180012d01  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012d06  mov     ebx, eax
0x180012d08  test    eax, eax
0x180012d0a  jns     short loc_180012D5D
0x180012d0c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012d13  jz      short loc_180012D38
0x180012d15  lea     rax, aChrMdmregistry_16; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012d1c  mov     [rsp+268h+var_240], rax
0x180012d21  mov     [rsp+268h+var_248], 150h
0x180012d29  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012d30  mov     r8d, ebx
0x180012d33  call    McTemplateU0dsqs_EventWriteTransfer
0x180012d38  cmp     ebx, 80070490h
0x180012d3e  jz      short loc_180012D48
0x180012d40  cmp     ebx, 80070002h
0x180012d46  jnz     short loc_180012D5D
0x180012d48  xor     ebx, ebx
0x180012d4a  mov     [rdi+10h], rbx
0x180012d4e  cmp     qword ptr [rdi+18h], 7
0x180012d53  jbe     short loc_180012D58
0x180012d55  mov     rdi, [rdi]
0x180012d58  xor     eax, eax
0x180012d5a  mov     [rdi], ax
0x180012d5d  mov     eax, ebx
0x180012d5f  mov     rcx, [rsp+268h+var_18]
0x180012d67  xor     rcx, rsp; StackCookie
0x180012d6a  call    __security_check_cookie
0x180012d6f  lea     r11, [rsp+268h+var_8]
0x180012d77  mov     rbx, [r11+10h]
0x180012d7b  mov     rsi, [r11+20h]
0x180012d7f  mov     rsp, r11
0x180012d82  pop     rdi
0x180012d83  retn
```
