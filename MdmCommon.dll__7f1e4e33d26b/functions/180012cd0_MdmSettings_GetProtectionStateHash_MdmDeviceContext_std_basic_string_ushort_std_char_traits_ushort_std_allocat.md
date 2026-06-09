# MdmSettings::GetProtectionStateHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012cd0`
- end: `0x180012e30`
- name: `?GetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005070`
- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180012cd0`
- `0x18001ce60`

## string_xrefs

- `0x180012d3e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012dd5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012d85`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012dc1`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetProtectionStateHash(int a1, _QWORD *a2)
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
          176,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"ProtectionStateHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        184,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      178,
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
0x180012cd0  mov     [rsp+arg_0], rbx
0x180012cd5  mov     [rsp+arg_10], rsi
0x180012cda  push    rdi
0x180012cdb  sub     rsp, 260h
0x180012ce2  mov     rax, cs:__security_cookie
0x180012ce9  xor     rax, rsp
0x180012cec  mov     [rsp+268h+var_18], rax
0x180012cf4  mov     rdi, rdx
0x180012cf7  mov     ebx, ecx
0x180012cf9  xor     edx, edx; Val
0x180012cfb  lea     rcx, [rsp+268h+var_228]; void *
0x180012d00  mov     r8d, 208h; Size
0x180012d06  call    memset_0
0x180012d0b  mov     [rsp+268h+var_238], 104h
0x180012d13  sub     ebx, 1
0x180012d16  jz      short loc_180012D60
0x180012d18  cmp     ebx, 1
0x180012d1b  jz      short loc_180012D57
0x180012d1d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012d24  mov     ebx, 80070057h
0x180012d29  jz      loc_180012E09
0x180012d2f  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012d36  mov     r8d, ebx
0x180012d39  mov     [rsp+268h+var_240], rax
0x180012d3e  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012d45  mov     [rsp+268h+var_248], 1B0h
0x180012d4d  call    McTemplateU0dsqs_EventWriteTransfer
0x180012d52  jmp     loc_180012E09
0x180012d57  mov     rsi, 0FFFFFFFF80000002h
0x180012d5e  jmp     short loc_180012D67
0x180012d60  mov     rsi, 0FFFFFFFF80000001h
0x180012d67  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012d6c  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012d71  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012d76  mov     ebx, eax
0x180012d78  test    eax, eax
0x180012d7a  jns     short loc_180012D9B
0x180012d7c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012d83  jz      short loc_180012DE4
0x180012d85  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012d8c  mov     [rsp+268h+var_240], rax
0x180012d91  mov     [rsp+268h+var_248], 1B2h
0x180012d99  jmp     short loc_180012DD5
0x180012d9b  mov     r9, rdi
0x180012d9e  lea     r8, aProtectionstat; "ProtectionStateHash"
0x180012da5  lea     rdx, [rsp+268h+var_228]
0x180012daa  mov     rcx, rsi
0x180012dad  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012db2  mov     ebx, eax
0x180012db4  test    eax, eax
0x180012db6  jns     short loc_180012E09
0x180012db8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012dbf  jz      short loc_180012DE4
0x180012dc1  lea     rax, aChrMdmregistry_18; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012dc8  mov     [rsp+268h+var_240], rax
0x180012dcd  mov     [rsp+268h+var_248], 1B8h
0x180012dd5  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012ddc  mov     r8d, ebx
0x180012ddf  call    McTemplateU0dsqs_EventWriteTransfer
0x180012de4  cmp     ebx, 80070490h
0x180012dea  jz      short loc_180012DF4
0x180012dec  cmp     ebx, 80070002h
0x180012df2  jnz     short loc_180012E09
0x180012df4  xor     ebx, ebx
0x180012df6  mov     [rdi+10h], rbx
0x180012dfa  cmp     qword ptr [rdi+18h], 7
0x180012dff  jbe     short loc_180012E04
0x180012e01  mov     rdi, [rdi]
0x180012e04  xor     eax, eax
0x180012e06  mov     [rdi], ax
0x180012e09  mov     eax, ebx
0x180012e0b  mov     rcx, [rsp+268h+var_18]
0x180012e13  xor     rcx, rsp; StackCookie
0x180012e16  call    __security_check_cookie
0x180012e1b  lea     r11, [rsp+268h+var_8]
0x180012e23  mov     rbx, [r11+10h]
0x180012e27  mov     rsi, [r11+20h]
0x180012e2b  mov     rsp, r11
0x180012e2e  pop     rdi
0x180012e2f  retn
```
