# GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)

- ea: `0x180012d8c`
- end: `0x180012dff`
- name: `?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z`
- size: `115`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `19`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d50`
- `0x180012954`
- `0x180012abc`
- `0x180012c24`
- `0x180012e08`
- `0x180012f70`
- `0x1800130b4`
- `0x180013280`
- `0x1800133e8`
- `0x1800137ac`
- `0x1800138dc`
- `0x180013a0c`
- `0x180013b3c`
- `0x180013c6c`
- `0x180013d9c`
- `0x180013f74`
- `0x1800140a4`
- `0x180014214`
- `0x180014344`

## callees

- `0x1800065c0`
- `0x180012d8c`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180012dab`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180012dab`

## string_xrefs

- `0x180012d9d`: `DeviceDirectoryClient`
- `0x180012da4`: `Software\Microsoft\MdmCommon\SettingValues`
- `0x180012dd3`: `CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( c_pszMdmCommonPersistedKeyId, c_pszGeneralSettingsKey, pwszPath, *pcchPath, pcchPath)))`
- `0x180012de2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`

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
      "CHR(HRESULT_FROM_WIN32(GetPersistedRegistryLocationW( c_pszMdmCommonPersistedKeyId, c_pszGeneralSettingsKey, pwszP"
      "ath, *pcchPath, pcchPath)))");
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012d8c  push    rbx
0x180012d8e  sub     rsp, 30h
0x180012d92  mov     r9d, [rdx]
0x180012d95  mov     r8, rcx
0x180012d98  mov     [rsp+38h+var_18], rdx
0x180012d9d  lea     rcx, aDevicedirector; "DeviceDirectoryClient"
0x180012da4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MdmCommon\\Setting"...
0x180012dab  call    cs:__imp_GetPersistedRegistryLocationW
0x180012db2  nop     dword ptr [rax+rax+00h]
0x180012db7  mov     ebx, eax
0x180012db9  test    eax, eax
0x180012dbb  jle     short loc_180012DC6
0x180012dbd  movzx   ebx, ax
0x180012dc0  or      ebx, 80070000h
0x180012dc6  test    ebx, ebx
0x180012dc8  jns     short loc_180012DF6
0x180012dca  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012dd1  jz      short loc_180012DF6
0x180012dd3  lea     rax, aChrHresultFrom; "CHR(HRESULT_FROM_WIN32(GetPersistedRegi"...
0x180012dda  mov     r8d, ebx
0x180012ddd  mov     [rsp+38h+var_10], rax
0x180012de2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012de9  mov     dword ptr [rsp+38h+var_18], 43h ; 'C'
0x180012df1  call    McTemplateU0dsqs_EventWriteTransfer
0x180012df6  mov     eax, ebx
0x180012df8  add     rsp, 30h
0x180012dfc  pop     rbx
0x180012dfd  retn
```
