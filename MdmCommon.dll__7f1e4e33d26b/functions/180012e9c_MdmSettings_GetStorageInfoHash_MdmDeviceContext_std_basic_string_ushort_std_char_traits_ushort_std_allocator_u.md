# MdmSettings::GetStorageInfoHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012e9c`
- end: `0x180012ffc`
- name: `?GetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180012e9c`
- `0x18001ce60`

## string_xrefs

- `0x180012f0a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012fa1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012f51`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012f8d`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszStorageInfoHash, pszValue))`

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
0x180012e9c  mov     [rsp+arg_0], rbx
0x180012ea1  mov     [rsp+arg_10], rsi
0x180012ea6  push    rdi
0x180012ea7  sub     rsp, 260h
0x180012eae  mov     rax, cs:__security_cookie
0x180012eb5  xor     rax, rsp
0x180012eb8  mov     [rsp+268h+var_18], rax
0x180012ec0  mov     rdi, rdx
0x180012ec3  mov     ebx, ecx
0x180012ec5  xor     edx, edx; Val
0x180012ec7  lea     rcx, [rsp+268h+var_228]; void *
0x180012ecc  mov     r8d, 208h; Size
0x180012ed2  call    memset_0
0x180012ed7  mov     [rsp+268h+var_238], 104h
0x180012edf  sub     ebx, 1
0x180012ee2  jz      short loc_180012F2C
0x180012ee4  cmp     ebx, 1
0x180012ee7  jz      short loc_180012F23
0x180012ee9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012ef0  mov     ebx, 80070057h
0x180012ef5  jz      loc_180012FD5
0x180012efb  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180012f02  mov     r8d, ebx
0x180012f05  mov     [rsp+268h+var_240], rax
0x180012f0a  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012f11  mov     [rsp+268h+var_248], 17Ch
0x180012f19  call    McTemplateU0dsqs_EventWriteTransfer
0x180012f1e  jmp     loc_180012FD5
0x180012f23  mov     rsi, 0FFFFFFFF80000002h
0x180012f2a  jmp     short loc_180012F33
0x180012f2c  mov     rsi, 0FFFFFFFF80000001h
0x180012f33  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012f38  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012f3d  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012f42  mov     ebx, eax
0x180012f44  test    eax, eax
0x180012f46  jns     short loc_180012F67
0x180012f48  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012f4f  jz      short loc_180012FB0
0x180012f51  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012f58  mov     [rsp+268h+var_240], rax
0x180012f5d  mov     [rsp+268h+var_248], 17Eh
0x180012f65  jmp     short loc_180012FA1
0x180012f67  mov     r9, rdi
0x180012f6a  lea     r8, aStorageinfohas; "StorageInfoHash"
0x180012f71  lea     rdx, [rsp+268h+var_228]
0x180012f76  mov     rcx, rsi
0x180012f79  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012f7e  mov     ebx, eax
0x180012f80  test    eax, eax
0x180012f82  jns     short loc_180012FD5
0x180012f84  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012f8b  jz      short loc_180012FB0
0x180012f8d  lea     rax, aChrMdmregistry_1; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012f94  mov     [rsp+268h+var_240], rax
0x180012f99  mov     [rsp+268h+var_248], 184h
0x180012fa1  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012fa8  mov     r8d, ebx
0x180012fab  call    McTemplateU0dsqs_EventWriteTransfer
0x180012fb0  cmp     ebx, 80070490h
0x180012fb6  jz      short loc_180012FC0
0x180012fb8  cmp     ebx, 80070002h
0x180012fbe  jnz     short loc_180012FD5
0x180012fc0  xor     ebx, ebx
0x180012fc2  mov     [rdi+10h], rbx
0x180012fc6  cmp     qword ptr [rdi+18h], 7
0x180012fcb  jbe     short loc_180012FD0
0x180012fcd  mov     rdi, [rdi]
0x180012fd0  xor     eax, eax
0x180012fd2  mov     [rdi], ax
0x180012fd5  mov     eax, ebx
0x180012fd7  mov     rcx, [rsp+268h+var_18]
0x180012fdf  xor     rcx, rsp; StackCookie
0x180012fe2  call    __security_check_cookie
0x180012fe7  lea     r11, [rsp+268h+var_8]
0x180012fef  mov     rbx, [r11+10h]
0x180012ff3  mov     rsi, [r11+20h]
0x180012ff7  mov     rsp, r11
0x180012ffa  pop     rdi
0x180012ffb  retn
```
