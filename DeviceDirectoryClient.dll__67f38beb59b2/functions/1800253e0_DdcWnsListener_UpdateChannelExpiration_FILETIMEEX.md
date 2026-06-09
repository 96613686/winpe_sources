# DdcWnsListener::UpdateChannelExpiration(FILETIMEEX)

- ea: `0x1800253e0`
- end: `0x1800254b8`
- name: `?UpdateChannelExpiration@DdcWnsListener@@SAJTFILETIMEEX@@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18001be44`
- `0x1800248e0`
- `0x1800253e0`

## string_xrefs

- `0x18002548e`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`
- `0x180025438`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszMdmSettingsKey, &cchMdmSettingsKey))`
- `0x18002547a`: `CHR(DdcRegistry::SetByteValue( (( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), wszMdmSettingsKey, REGISTRY_VALUE_CHANNEL_URL_EXPIRATION, (BYTE *)&ftExpiration, (DWORD)sizeof(FILETIMEEX)))`

## pseudocode

```c
__int64 __fastcall DdcWnsListener::UpdateChannelExpiration(__int64 a1)
{
  int v1; // edx
  int v2; // ecx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  int v4; // edx
  int v5; // ecx
  unsigned int v7; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int8 v8[8]; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-228h] BYREF

  *(_QWORD *)v8 = a1;
  memset_0(v9, 0, 0x208u);
  v7 = 260;
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v9, &v7);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = DdcRegistry::SetByteValue(
                                                HKEY_LOCAL_MACHINE,
                                                v9,
                                                L"ChannelUrlExpiration",
                                                v8);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
        124,
        "CHR(DdcRegistry::SetByteValue( (( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), wszMdmSettingsKey, REGISTRY_VALUE_CHAN"
        "NEL_URL_EXPIRATION, (BYTE *)&ftExpiration, (DWORD)sizeof(FILETIMEEX)))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v2,
      v1,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
      118,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszMdmSettingsKey, &cchMdmSettingsKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800253e0  push    rbx
0x1800253e2  sub     rsp, 260h
0x1800253e9  mov     rax, cs:__security_cookie
0x1800253f0  xor     rax, rsp
0x1800253f3  mov     [rsp+268h+var_18], rax
0x1800253fb  mov     qword ptr [rsp+268h+var_230], rcx
0x180025400  xor     edx, edx; Val
0x180025402  lea     rcx, [rsp+268h+var_228]; void *
0x180025407  mov     r8d, 208h; Size
0x18002540d  call    memset_0
0x180025412  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180025417  mov     [rsp+268h+var_238], 104h
0x18002541f  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180025424  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180025429  mov     ebx, eax
0x18002542b  test    eax, eax
0x18002542d  jns     short loc_18002544E
0x18002542f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025436  jz      short loc_18002549D
0x180025438  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x18002543f  mov     [rsp+268h+var_240], rax
0x180025444  mov     [rsp+268h+var_248], 76h ; 'v'
0x18002544c  jmp     short loc_18002548E
0x18002544e  lea     r9, [rsp+268h+var_230]; unsigned __int8 *
0x180025453  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002545a  lea     r8, aChannelurlexpi; "ChannelUrlExpiration"
0x180025461  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x180025466  call    ?SetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1PEAEKK@Z; DdcRegistry::SetByteValue(HKEY__ *,ushort const *,ushort const *,uchar *,ulong,ulong)
0x18002546b  mov     ebx, eax
0x18002546d  test    eax, eax
0x18002546f  jns     short loc_18002549D
0x180025471  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025478  jz      short loc_18002549D
0x18002547a  lea     rax, aChrDdcregistry; "CHR(DdcRegistry::SetByteValue( (( HKEY "...
0x180025481  mov     [rsp+268h+var_240], rax
0x180025486  mov     [rsp+268h+var_248], 7Ch ; '|'
0x18002548e  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180025495  mov     r8d, ebx
0x180025498  call    McTemplateU0dsqs_EventWriteTransfer
0x18002549d  mov     eax, ebx
0x18002549f  mov     rcx, [rsp+268h+var_18]
0x1800254a7  xor     rcx, rsp; StackCookie
0x1800254aa  call    __security_check_cookie
0x1800254af  add     rsp, 260h
0x1800254b6  pop     rbx
0x1800254b7  retn
```
