# MdmSettings::SetRegisteredWithService(MdmDeviceContext,int)

- ea: `0x180013ca4`
- end: `0x180013e0a`
- name: `?SetRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@H@Z`
- size: `358`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001142c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180013ca4`
- `0x18001d0d0`
- `0x18001d138`

## string_xrefs

- `0x180013d62`: `RegisteredWithService`
- `0x180013dd8`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013d46`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013d85`: `CHR(MdmRegistry::SetBOOLValue( hKey, wszKey, c_pszRegisteredWithService, fRegistered))`
- `0x180013dc4`: `CHR(MdmRegistry::SetDWORDValue( hKey, wszKey, c_pszRegisteredVersion, 6))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetRegisteredWithService(int a1)
{
  int v2; // edx
  int v3; // ecx
  int v4; // ebx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v6; // rdi
  int v7; // edx
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  unsigned int v14[4]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v15, 0, 0x208u);
  v14[0] = 260;
  v4 = a1 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
    {
      MdmCommonSettingValuesPersistedLocation = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v3,
          v2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          211,
          "CBR(hKey != nullptr)",
          *(_QWORD *)v14);
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    }
    v6 = -2147483646;
  }
  else
  {
    v6 = -2147483647;
  }
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v15, v14);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetBOOLValue((HKEY)v6, v15, L"RegisteredWithService", 1);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
    {
      MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetDWORDValue((HKEY)v6, v15, L"RegisteredVersion", 6);
      if ( MdmCommonSettingValuesPersistedLocation < 0
        && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          MdmCommonSettingValuesPersistedLocation,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          225,
          "CHR(MdmRegistry::SetDWORDValue( hKey, wszKey, c_pszRegisteredVersion, 6))",
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
        219,
        "CHR(MdmRegistry::SetBOOLValue( hKey, wszKey, c_pszRegisteredWithService, fRegistered))",
        *(_QWORD *)v14);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      213,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013ca4  mov     [rsp+arg_0], rbx
0x180013ca9  push    rdi
0x180013caa  sub     rsp, 260h
0x180013cb1  mov     rax, cs:__security_cookie
0x180013cb8  xor     rax, rsp
0x180013cbb  mov     [rsp+268h+var_18], rax
0x180013cc3  mov     ebx, ecx
0x180013cc5  xor     edx, edx; Val
0x180013cc7  lea     rcx, [rsp+268h+var_228]; void *
0x180013ccc  mov     r8d, 208h; Size
0x180013cd2  call    memset_0
0x180013cd7  mov     [rsp+268h+var_238], 104h
0x180013cdf  sub     ebx, 1
0x180013ce2  jz      short loc_180013D1D
0x180013ce4  cmp     ebx, 1
0x180013ce7  jz      short loc_180013D14
0x180013ce9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013cf0  mov     ebx, 80070057h
0x180013cf5  jz      loc_180013DE7
0x180013cfb  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013d02  mov     [rsp+268h+var_240], rax
0x180013d07  mov     [rsp+268h+var_248], 2D3h
0x180013d0f  jmp     loc_180013DD8
0x180013d14  mov     rdi, 0FFFFFFFF80000002h
0x180013d1b  jmp     short loc_180013D24
0x180013d1d  mov     rdi, 0FFFFFFFF80000001h
0x180013d24  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013d29  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013d2e  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013d33  mov     ebx, eax
0x180013d35  test    eax, eax
0x180013d37  jns     short loc_180013D5C
0x180013d39  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013d40  jz      loc_180013DE7
0x180013d46  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013d4d  mov     [rsp+268h+var_240], rax
0x180013d52  mov     [rsp+268h+var_248], 2D5h
0x180013d5a  jmp     short loc_180013DD8
0x180013d5c  mov     r9d, 1; int
0x180013d62  lea     r8, aRegisteredwith; "RegisteredWithService"
0x180013d69  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x180013d6e  mov     rcx, rdi; HKEY
0x180013d71  call    ?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z; MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)
0x180013d76  mov     ebx, eax
0x180013d78  test    eax, eax
0x180013d7a  jns     short loc_180013D9B
0x180013d7c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013d83  jz      short loc_180013DE7
0x180013d85  lea     rax, aChrMdmregistry_0; "CHR(MdmRegistry::SetBOOLValue( hKey, ws"...
0x180013d8c  mov     [rsp+268h+var_240], rax
0x180013d91  mov     [rsp+268h+var_248], 2DBh
0x180013d99  jmp     short loc_180013DD8
0x180013d9b  mov     r9d, 6; unsigned int
0x180013da1  lea     r8, aRegisteredvers; "RegisteredVersion"
0x180013da8  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x180013dad  mov     rcx, rdi; HKEY
0x180013db0  call    ?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z; MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x180013db5  mov     ebx, eax
0x180013db7  test    eax, eax
0x180013db9  jns     short loc_180013DE7
0x180013dbb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013dc2  jz      short loc_180013DE7
0x180013dc4  lea     rax, aChrMdmregistry_4; "CHR(MdmRegistry::SetDWORDValue( hKey, w"...
0x180013dcb  mov     [rsp+268h+var_240], rax
0x180013dd0  mov     [rsp+268h+var_248], 2E1h
0x180013dd8  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013ddf  mov     r8d, ebx
0x180013de2  call    McTemplateU0dsqs_EventWriteTransfer
0x180013de7  mov     eax, ebx
0x180013de9  mov     rcx, [rsp+268h+var_18]
0x180013df1  xor     rcx, rsp; StackCookie
0x180013df4  call    __security_check_cookie
0x180013df9  mov     rbx, [rsp+268h+arg_0]
0x180013e01  add     rsp, 260h
0x180013e08  pop     rdi
0x180013e09  retn
```
