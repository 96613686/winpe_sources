# MdmSettings::SetRegisteredWithService(MdmDeviceContext,int)

- ea: `0x1800140a4`
- end: `0x18001420b`
- name: `?SetRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@H@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011800`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x1800140a4`
- `0x18001d77c`
- `0x18001d7e4`

## string_xrefs

- `0x180014162`: `RegisteredWithService`
- `0x1800141d8`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180014146`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180014185`: `CHR(MdmRegistry::SetBOOLValue( hKey, wszKey, c_pszRegisteredWithService, fRegistered))`
- `0x1800141c4`: `CHR(MdmRegistry::SetDWORDValue( hKey, wszKey, c_pszRegisteredVersion, 6))`

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
  unsigned int v14; // [rsp+20h] [rbp-248h]
  unsigned int v15[4]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v16[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v16, 0, 0x208u);
  v15[0] = 260;
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
          *(_QWORD *)v15);
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    }
    v6 = -2147483646;
  }
  else
  {
    v6 = -2147483647;
  }
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v16, v15);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetBOOLValue((HKEY)v6, v16, L"RegisteredWithService", 1, v14);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
    {
      MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetDWORDValue((HKEY)v6, v16, L"RegisteredVersion", 6);
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
          *(_QWORD *)v15);
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
        *(_QWORD *)v15);
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
      *(_QWORD *)v15);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800140a4  mov     [rsp+arg_0], rbx
0x1800140a9  push    rdi
0x1800140aa  sub     rsp, 260h
0x1800140b1  mov     rax, cs:__security_cookie
0x1800140b8  xor     rax, rsp
0x1800140bb  mov     [rsp+268h+var_18], rax
0x1800140c3  mov     ebx, ecx
0x1800140c5  xor     edx, edx; Val
0x1800140c7  lea     rcx, [rsp+268h+var_228]; void *
0x1800140cc  mov     r8d, 208h; Size
0x1800140d2  call    memset_0
0x1800140d7  mov     [rsp+268h+var_238], 104h
0x1800140df  sub     ebx, 1
0x1800140e2  jz      short loc_18001411D
0x1800140e4  cmp     ebx, 1
0x1800140e7  jz      short loc_180014114
0x1800140e9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800140f0  mov     ebx, 80070057h
0x1800140f5  jz      loc_1800141E7
0x1800140fb  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180014102  mov     [rsp+268h+var_240], rax
0x180014107  mov     [rsp+268h+var_248], 2D3h
0x18001410f  jmp     loc_1800141D8
0x180014114  mov     rdi, 0FFFFFFFF80000002h
0x18001411b  jmp     short loc_180014124
0x18001411d  mov     rdi, 0FFFFFFFF80000001h
0x180014124  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180014129  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001412e  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180014133  mov     ebx, eax
0x180014135  test    eax, eax
0x180014137  jns     short loc_18001415C
0x180014139  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014140  jz      loc_1800141E7
0x180014146  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x18001414d  mov     [rsp+268h+var_240], rax
0x180014152  mov     [rsp+268h+var_248], 2D5h
0x18001415a  jmp     short loc_1800141D8
0x18001415c  mov     r9d, 1; int
0x180014162  lea     r8, aRegisteredwith; "RegisteredWithService"
0x180014169  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x18001416e  mov     rcx, rdi; HKEY
0x180014171  call    ?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z; MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)
0x180014176  mov     ebx, eax
0x180014178  test    eax, eax
0x18001417a  jns     short loc_18001419B
0x18001417c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014183  jz      short loc_1800141E7
0x180014185  lea     rax, aChrMdmregistry_0; "CHR(MdmRegistry::SetBOOLValue( hKey, ws"...
0x18001418c  mov     [rsp+268h+var_240], rax
0x180014191  mov     [rsp+268h+var_248], 2DBh
0x180014199  jmp     short loc_1800141D8
0x18001419b  mov     r9d, 6; unsigned int
0x1800141a1  lea     r8, aRegisteredvers; "RegisteredVersion"
0x1800141a8  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x1800141ad  mov     rcx, rdi; HKEY
0x1800141b0  call    ?SetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1KK@Z; MdmRegistry::SetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong)
0x1800141b5  mov     ebx, eax
0x1800141b7  test    eax, eax
0x1800141b9  jns     short loc_1800141E7
0x1800141bb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800141c2  jz      short loc_1800141E7
0x1800141c4  lea     rax, aChrMdmregistry_4; "CHR(MdmRegistry::SetDWORDValue( hKey, w"...
0x1800141cb  mov     [rsp+268h+var_240], rax
0x1800141d0  mov     [rsp+268h+var_248], 2E1h
0x1800141d8  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800141df  mov     r8d, ebx
0x1800141e2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800141e7  mov     eax, ebx
0x1800141e9  mov     rcx, [rsp+268h+var_18]
0x1800141f1  xor     rcx, rsp; StackCookie
0x1800141f4  call    __security_check_cookie
0x1800141f9  mov     rbx, [rsp+268h+arg_0]
0x180014201  add     rsp, 260h
0x180014208  pop     rdi
0x180014209  retn
```
