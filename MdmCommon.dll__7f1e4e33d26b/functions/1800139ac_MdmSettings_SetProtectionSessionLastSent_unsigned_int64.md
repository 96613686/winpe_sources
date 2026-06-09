# MdmSettings::SetProtectionSessionLastSent(unsigned __int64)

- ea: `0x1800139ac`
- end: `0x180013b6b`
- name: `?SetProtectionSessionLastSent@MdmSettings@@SAJ_K@Z`
- size: `447`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001142c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x1800139ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ad8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ad8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013a68`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013a68`

## string_xrefs

- `0x180013b41`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013a08`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013b2d`: `CHR(MdmRegistry::SetByteValue( wszKey, c_pszProtectionSessionLastSent, (BYTE *)&ullValue, sizeof(ullValue)))`
- `0x180013aa0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
0x1800139ac  push    rbx
0x1800139ae  sub     rsp, 290h
0x1800139b5  mov     rax, cs:__security_cookie
0x1800139bc  xor     rax, rsp
0x1800139bf  mov     [rsp+298h+var_18], rax
0x1800139c7  mov     qword ptr [rsp+298h+Data], rcx
0x1800139cc  xor     edx, edx; Val
0x1800139ce  lea     rcx, [rsp+298h+SubKey]; void *
0x1800139d3  mov     r8d, 208h; Size
0x1800139d9  call    memset_0
0x1800139de  lea     rdx, [rsp+298h+var_248]; unsigned int *
0x1800139e3  mov     [rsp+298h+var_248], 104h
0x1800139eb  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x1800139f0  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800139f5  mov     ebx, eax
0x1800139f7  test    eax, eax
0x1800139f9  jns     short loc_180013A21
0x1800139fb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013a02  jz      loc_180013B50
0x180013a08  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013a0f  mov     qword ptr [rsp+298h+samDesired], rax
0x180013a14  mov     [rsp+298h+dwOptions], 97h
0x180013a1c  jmp     loc_180013B41
0x180013a21  mov     [rsp+298h+lpdwDisposition], 0; lpdwDisposition
0x180013a2a  lea     rax, [rsp+298h+hKey]
0x180013a2f  mov     [rsp+298h+phkResult], rax; phkResult
0x180013a34  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180013a39  mov     [rsp+298h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013a42  xor     r9d, r9d; lpClass
0x180013a45  mov     [rsp+298h+samDesired], 0F003Fh; samDesired
0x180013a4d  xor     r8d, r8d; Reserved
0x180013a50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013a57  mov     [rsp+298h+dwOptions], 0; dwOptions
0x180013a5f  mov     [rsp+298h+hKey], 0
0x180013a68  call    cs:__imp_RegCreateKeyExW
0x180013a6e  mov     ebx, eax
0x180013a70  test    eax, eax
0x180013a72  jz      short loc_180013AB1
0x180013a74  jle     short loc_180013A7F
0x180013a76  movzx   ebx, ax
0x180013a79  or      ebx, 80070000h
0x180013a7f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013a86  jz      loc_180013B10
0x180013a8c  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x180013a93  mov     qword ptr [rsp+298h+samDesired], rax
0x180013a98  mov     [rsp+298h+dwOptions], 75h ; 'u'
0x180013aa0  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013aa7  mov     r8d, ebx
0x180013aaa  call    McTemplateU0dsqs_EventWriteTransfer
0x180013aaf  jmp     short loc_180013B10
0x180013ab1  mov     rcx, [rsp+298h+hKey]; hKey
0x180013ab6  lea     rax, [rsp+298h+Data]
0x180013abb  mov     [rsp+298h+samDesired], 8; cbData
0x180013ac3  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x180013aca  mov     r9d, 3; dwType
0x180013ad0  mov     qword ptr [rsp+298h+dwOptions], rax; lpData
0x180013ad5  xor     r8d, r8d; Reserved
0x180013ad8  call    cs:__imp_RegSetValueExW
0x180013ade  mov     ebx, eax
0x180013ae0  test    eax, eax
0x180013ae2  jz      short loc_180013B0E
0x180013ae4  jle     short loc_180013AEF
0x180013ae6  movzx   ebx, ax
0x180013ae9  or      ebx, 80070000h
0x180013aef  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013af6  jz      short loc_180013B10
0x180013af8  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x180013aff  mov     qword ptr [rsp+298h+samDesired], rax
0x180013b04  mov     [rsp+298h+dwOptions], 7Fh
0x180013b0c  jmp     short loc_180013AA0
0x180013b0e  xor     ebx, ebx
0x180013b10  mov     rcx, [rsp+298h+hKey]; hKey
0x180013b15  test    rcx, rcx
0x180013b18  jz      short loc_180013B20
0x180013b1a  call    cs:__imp_RegCloseKey
0x180013b20  test    ebx, ebx
0x180013b22  jns     short loc_180013B50
0x180013b24  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013b2b  jz      short loc_180013B50
0x180013b2d  lea     rax, aChrMdmregistry_15; "CHR(MdmRegistry::SetByteValue( wszKey, "...
0x180013b34  mov     qword ptr [rsp+298h+samDesired], rax
0x180013b39  mov     [rsp+298h+dwOptions], 9Dh
0x180013b41  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013b48  mov     r8d, ebx
0x180013b4b  call    McTemplateU0dsqs_EventWriteTransfer
0x180013b50  mov     eax, ebx
0x180013b52  mov     rcx, [rsp+298h+var_18]
0x180013b5a  xor     rcx, rsp; StackCookie
0x180013b5d  call    __security_check_cookie
0x180013b62  add     rsp, 290h
0x180013b69  pop     rbx
0x180013b6a  retn
```
