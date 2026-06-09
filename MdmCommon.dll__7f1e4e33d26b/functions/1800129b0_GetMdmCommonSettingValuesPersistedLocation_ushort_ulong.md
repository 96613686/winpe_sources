# GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)

- ea: `0x1800129b0`
- end: `0x180012a1c`
- name: `?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z`
- size: `108`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d40`
- `0x180012578`
- `0x1800126e0`
- `0x180012848`
- `0x180012a24`
- `0x180012b8c`
- `0x180012cd0`
- `0x180012e9c`
- `0x180013004`
- `0x1800133bc`
- `0x1800134ec`
- `0x18001361c`
- `0x18001374c`
- `0x18001387c`
- `0x1800139ac`
- `0x180013b74`
- `0x180013ca4`
- `0x180013e10`
- `0x180013f40`

## callees

- `0x180006548`
- `0x1800129b0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800129cf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800129cf`

## string_xrefs

- `0x1800129c1`: `DeviceDirectoryClient`
- `0x1800129c8`: `Software\Microsoft\MdmCommon\SettingValues`
- `0x1800129f1`: `CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( c_pszMdmCommonPersistedKeyId, c_pszGeneralSettingsKey, pwszPath, *pcchPath, pcchPath)))`
- `0x180012a00`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`

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
  if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      v3,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      67,
      (__int64)"CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( c_pszMdmCommonPersistedKeyId, c_pszGeneralSettingsK"
               "ey, pwszPath, *pcchPath, pcchPath)))");
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800129b0  push    rbx
0x1800129b2  sub     rsp, 30h
0x1800129b6  mov     r9d, [rdx]
0x1800129b9  mov     r8, rcx
0x1800129bc  mov     [rsp+38h+var_18], rdx
0x1800129c1  lea     rcx, aDevicedirector; "DeviceDirectoryClient"
0x1800129c8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MdmCommon\\Setting"...
0x1800129cf  call    cs:__imp_GetPersistedRegistryLocationW
0x1800129d5  mov     ebx, eax
0x1800129d7  test    eax, eax
0x1800129d9  jle     short loc_1800129E4
0x1800129db  movzx   ebx, ax
0x1800129de  or      ebx, 80070000h
0x1800129e4  test    ebx, ebx
0x1800129e6  jns     short loc_180012A14
0x1800129e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800129ef  jz      short loc_180012A14
0x1800129f1  lea     rax, aChrHresultFrom; "CHR(HRESULT_FROM_WIN32(GetPersistedRegi"...
0x1800129f8  mov     r8d, ebx
0x1800129fb  mov     [rsp+38h+var_10], rax
0x180012a00  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012a07  mov     dword ptr [rsp+38h+var_18], 43h ; 'C'
0x180012a0f  call    McTemplateU0dsqs_EventWriteTransfer
0x180012a14  mov     eax, ebx
0x180012a16  add     rsp, 30h
0x180012a1a  pop     rbx
0x180012a1b  retn
```
