# MdmSettings::SetProtectionSessionLastSent(unsigned __int64)

- ea: `0x180013d9c`
- end: `0x180013f6e`
- name: `?SetProtectionSessionLastSent@MdmSettings@@SAJ_K@Z`
- size: `466`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011800`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180013d9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ece`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ece`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013e58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013e58`

## string_xrefs

- `0x180013f43`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013df8`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013f2f`: `CHR(MdmRegistry::SetByteValue( wszKey, c_pszProtectionSessionLastSent, (BYTE *)&ullValue, sizeof(ullValue)))`
- `0x180013e96`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetProtectionSessionLastSent(__int64 a1)
{
  int v1; // edx
  int v2; // ecx
  signed int MdmCommonSettingValuesPersistedLocation; // ebx
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // ecx
  LSTATUS v7; // eax
  int v8; // ecx
  int v9; // ecx
  unsigned int v11; // [rsp+50h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-240h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-228h] BYREF

  *(_QWORD *)Data = a1;
  memset_0(SubKey, 0, 0x208u);
  v11 = 260;
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(SubKey, &v11);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    hKey = 0;
    v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    MdmCommonSettingValuesPersistedLocation = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        MdmCommonSettingValuesPersistedLocation = (unsigned __int16)v4 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          MdmCommonSettingValuesPersistedLocation,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          117,
          "CBR(0L == dwResult)");
    }
    else
    {
      v7 = RegSetValueExW(hKey, L"ProtectionSessionLastSent", 0, 3u, Data, 8u);
      MdmCommonSettingValuesPersistedLocation = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          MdmCommonSettingValuesPersistedLocation = (unsigned __int16)v7 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v8,
            v5,
            MdmCommonSettingValuesPersistedLocation,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
            127,
            "CBR(0L == dwResult)");
      }
      else
      {
        MdmCommonSettingValuesPersistedLocation = 0;
      }
    }
    v9 = (int)hKey;
    if ( hKey )
      RegCloseKey(hKey);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v5,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        157,
        "CHR(MdmRegistry::SetByteValue( wszKey, c_pszProtectionSessionLastSent, (BYTE *)&ullValue, sizeof(ullValue)))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v2,
      v1,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      151,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013d9c  push    rbx
0x180013d9e  sub     rsp, 290h
0x180013da5  mov     rax, cs:__security_cookie
0x180013dac  xor     rax, rsp
0x180013daf  mov     [rsp+298h+var_18], rax
0x180013db7  mov     qword ptr [rsp+298h+Data], rcx
0x180013dbc  xor     edx, edx; Val
0x180013dbe  lea     rcx, [rsp+298h+SubKey]; void *
0x180013dc3  mov     r8d, 208h; Size
0x180013dc9  call    memset_0
0x180013dce  lea     rdx, [rsp+298h+var_248]; unsigned int *
0x180013dd3  mov     [rsp+298h+var_248], 104h
0x180013ddb  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x180013de0  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013de5  mov     ebx, eax
0x180013de7  test    eax, eax
0x180013de9  jns     short loc_180013E11
0x180013deb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013df2  jz      loc_180013F52
0x180013df8  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013dff  mov     qword ptr [rsp+298h+samDesired], rax
0x180013e04  mov     [rsp+298h+dwOptions], 97h
0x180013e0c  jmp     loc_180013F43
0x180013e11  mov     [rsp+298h+lpdwDisposition], 0; lpdwDisposition
0x180013e1a  lea     rax, [rsp+298h+hKey]
0x180013e1f  mov     [rsp+298h+phkResult], rax; phkResult
0x180013e24  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180013e29  mov     [rsp+298h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013e32  xor     r9d, r9d; lpClass
0x180013e35  mov     [rsp+298h+samDesired], 0F003Fh; samDesired
0x180013e3d  xor     r8d, r8d; Reserved
0x180013e40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013e47  mov     [rsp+298h+dwOptions], 0; dwOptions
0x180013e4f  mov     [rsp+298h+hKey], 0
0x180013e58  call    cs:__imp_RegCreateKeyExW
0x180013e5f  nop     dword ptr [rax+rax+00h]
0x180013e64  mov     ebx, eax
0x180013e66  test    eax, eax
0x180013e68  jz      short loc_180013EA7
0x180013e6a  jle     short loc_180013E75
0x180013e6c  movzx   ebx, ax
0x180013e6f  or      ebx, 80070000h
0x180013e75  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013e7c  jz      loc_180013F0C
0x180013e82  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x180013e89  mov     qword ptr [rsp+298h+samDesired], rax
0x180013e8e  mov     [rsp+298h+dwOptions], 75h ; 'u'
0x180013e96  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013e9d  mov     r8d, ebx
0x180013ea0  call    McTemplateU0dsqs_EventWriteTransfer
0x180013ea5  jmp     short loc_180013F0C
0x180013ea7  mov     rcx, [rsp+298h+hKey]; hKey
0x180013eac  lea     rax, [rsp+298h+Data]
0x180013eb1  mov     [rsp+298h+samDesired], 8; cbData
0x180013eb9  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x180013ec0  mov     r9d, 3; dwType
0x180013ec6  mov     qword ptr [rsp+298h+dwOptions], rax; lpData
0x180013ecb  xor     r8d, r8d; Reserved
0x180013ece  call    cs:__imp_RegSetValueExW
0x180013ed5  nop     dword ptr [rax+rax+00h]
0x180013eda  mov     ebx, eax
0x180013edc  test    eax, eax
0x180013ede  jz      short loc_180013F0A
0x180013ee0  jle     short loc_180013EEB
0x180013ee2  movzx   ebx, ax
0x180013ee5  or      ebx, 80070000h
0x180013eeb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013ef2  jz      short loc_180013F0C
0x180013ef4  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x180013efb  mov     qword ptr [rsp+298h+samDesired], rax
0x180013f00  mov     [rsp+298h+dwOptions], 7Fh
0x180013f08  jmp     short loc_180013E96
0x180013f0a  xor     ebx, ebx
0x180013f0c  mov     rcx, [rsp+298h+hKey]; hKey
0x180013f11  test    rcx, rcx
0x180013f14  jz      short loc_180013F22
0x180013f16  call    cs:__imp_RegCloseKey
0x180013f1d  nop     dword ptr [rax+rax+00h]
0x180013f22  test    ebx, ebx
0x180013f24  jns     short loc_180013F52
0x180013f26  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013f2d  jz      short loc_180013F52
0x180013f2f  lea     rax, aChrMdmregistry_15; "CHR(MdmRegistry::SetByteValue( wszKey, "...
0x180013f36  mov     qword ptr [rsp+298h+samDesired], rax
0x180013f3b  mov     [rsp+298h+dwOptions], 9Dh
0x180013f43  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013f4a  mov     r8d, ebx
0x180013f4d  call    McTemplateU0dsqs_EventWriteTransfer
0x180013f52  mov     eax, ebx
0x180013f54  mov     rcx, [rsp+298h+var_18]
0x180013f5c  xor     rcx, rsp; StackCookie
0x180013f5f  call    __security_check_cookie
0x180013f64  add     rsp, 290h
0x180013f6b  pop     rbx
0x180013f6c  retn
```
