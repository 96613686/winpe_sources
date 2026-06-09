# GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)

- ea: `0x1800248e0`
- end: `0x18002494c`
- name: `?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024d9c`
- `0x1800253e0`

## callees

- `0x1800050b8`
- `0x1800248e0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800248ff`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800248ff`

## string_xrefs

- `0x1800248f1`: `DeviceDirectoryClient`
- `0x1800248f8`: `Software\Microsoft\MdmCommon\SettingValues`
- `0x180024921`: `CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( wszMdmCommonPersistedKeyId, wszMdmCommonSettingsKey, pwszPath, *pcchPath, pcchPath)))`
- `0x180024930`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`

## pseudocode

```c
__int64 __fastcall GetMdmCommonSettingValuesPersistedLocation(unsigned __int16 *a1, unsigned int *a2)
{
  int PersistedRegistryLocationW; // eax
  int v3; // edx
  int v4; // ecx
  signed int v5; // ebx

  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceDirectoryClient",
                                 L"Software\\Microsoft\\MdmCommon\\SettingValues",
                                 a1,
                                 *a2,
                                 a2);
  v5 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW > 0 )
    v5 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      v3,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
      48,
      "CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( wszMdmCommonPersistedKeyId, wszMdmCommonSettingsKey, pwszPat"
      "h, *pcchPath, pcchPath)))");
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800248e0  push    rbx
0x1800248e2  sub     rsp, 30h
0x1800248e6  mov     r9d, [rdx]
0x1800248e9  mov     r8, rcx
0x1800248ec  mov     [rsp+38h+var_18], rdx
0x1800248f1  lea     rcx, aDevicedirector_1; "DeviceDirectoryClient"
0x1800248f8  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Setting"...
0x1800248ff  call    cs:__imp_GetPersistedRegistryLocationW
0x180024905  mov     ebx, eax
0x180024907  test    eax, eax
0x180024909  jle     short loc_180024914
0x18002490b  movzx   ebx, ax
0x18002490e  or      ebx, 80070000h
0x180024914  test    ebx, ebx
0x180024916  jns     short loc_180024944
0x180024918  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002491f  jz      short loc_180024944
0x180024921  lea     rax, aChrHresultFrom_1; "CHR(HRESULT_FROM_WIN32(GetPersistedRegi"...
0x180024928  mov     r8d, ebx
0x18002492b  mov     [rsp+38h+var_10], rax
0x180024930  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180024937  mov     dword ptr [rsp+38h+var_18], 30h ; '0'
0x18002493f  call    McTemplateU0dsqs_EventWriteTransfer
0x180024944  mov     eax, ebx
0x180024946  add     rsp, 30h
0x18002494a  pop     rbx
0x18002494b  retn
```
