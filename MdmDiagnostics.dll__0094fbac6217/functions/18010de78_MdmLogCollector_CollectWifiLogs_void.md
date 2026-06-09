# MdmLogCollector::CollectWifiLogs(void)

- ea: `0x18010de78`
- end: `0x18010e096`
- name: `?CollectWifiLogs@MdmLogCollector@@AEAAJXZ`
- size: `542`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x18001a0a0`
- `0x1800e66dc`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x18010de78`
- `0x1801100e4`
- `0x1801107fc`
- `0x180110dd8`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010dee6`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010dee6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e03e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010e03e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18010df87`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18010df87`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010defd`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010defd`

## string_xrefs

- `0x18010df9d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e014`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e04f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010df2e`: `"%s\logman.exe" update WiFiSession -fd -ets`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmLogCollector::CollectWifiLogs(MdmLogCollector *this)
{
  HRESULT updated; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  const WCHAR *v5; // rax
  HRESULT v6; // eax
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  memset(v12, 0, sizeof(v12));
  ppszPath = 0;
  v9 = 0;
  v11 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v9, &v11);
  updated = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  LastError = updated;
  if ( updated < 0 )
  {
    v4 = 1912;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)updated,
      v9);
    goto LABEL_18;
  }
  if ( v9 == 16 || v9 == 10 )
  {
    updated = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                v12,
                L"\"%s\\tracelog.exe\" -capturestate -systemrundown -flush WifiSession",
                ppszPath);
    LastError = updated;
    if ( updated < 0 )
    {
      v4 = 1919;
      goto LABEL_14;
    }
    if ( !ExpandEnvironmentStringsW(L"%OSDataDrive%\\systemdata\\etw\\WiFi.etl*", pszPath, 0x104u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x782,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                    v7);
      goto LABEL_18;
    }
LABEL_10:
    wprintf(L"Collecting Wifi Session information.  This may take up to two minutes...\n");
    updated = MdmLogCollector::UpdateWifiEtl(this, v12[0], pszPath);
    LastError = updated;
    if ( updated >= 0 )
    {
      LastError = 0;
      goto LABEL_18;
    }
    v4 = 1937;
    goto LABEL_14;
  }
  updated = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v12,
              L"\"%s\\logman.exe\" update WiFiSession -fd -ets",
              ppszPath);
  LastError = updated;
  if ( updated < 0 )
  {
    v4 = 1929;
    goto LABEL_14;
  }
  std::wstring::wstring(v13, ppszPath);
  std::wstring::append(v13, L"\\logfiles\\wmi\\WiFi.etl");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = PathCchAppend(pszPath, 0x104u, v5);
  LastError = v6;
  if ( v6 >= 0 )
  {
    std::wstring::_Tidy_deallocate(v13);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x78D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
    (const char *)(unsigned int)v6,
    v9);
  std::wstring::_Tidy_deallocate(v13);
LABEL_18:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
  return LastError;
}

```

## disassembly

```asm
0x18010de78  mov     [rsp-8+arg_8], rbx
0x18010de7d  mov     [rsp-8+arg_10], rdi
0x18010de82  push    rbp
0x18010de83  lea     rbp, [rsp-190h]
0x18010de8b  sub     rsp, 290h
0x18010de92  mov     rax, cs:__security_cookie
0x18010de99  xor     rax, rsp
0x18010de9c  mov     [rbp+190h+var_10], rax
0x18010dea3  mov     rdi, rcx
0x18010dea6  mov     [rsp+290h+var_258], 0
0x18010deaf  mov     [rsp+290h+var_250], 0
0x18010deb8  mov     [rsp+290h+var_248], 0
0x18010dec1  mov     [rsp+290h+ppszPath], 0
0x18010deca  mov     [rsp+290h+var_270], 0; int
0x18010ded2  mov     [rsp+290h+var_260], 0
0x18010deda  lea     r8, [rsp+290h+var_260]
0x18010dedf  lea     rdx, [rsp+290h+var_270]
0x18010dee4  xor     ecx, ecx
0x18010dee6  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18010deec  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x18010def1  xor     r8d, r8d; hToken
0x18010def4  xor     edx, edx; dwFlags
0x18010def6  lea     rcx, FOLDERID_System; rfid
0x18010defd  call    cs:__imp_SHGetKnownFolderPath
0x18010df03  mov     ebx, eax
0x18010df05  test    eax, eax
0x18010df07  jns     short loc_18010DF13
0x18010df09  mov     edx, 778h
0x18010df0e  jmp     loc_18010E014
0x18010df13  cmp     [rsp+290h+var_270], 10h
0x18010df18  jz      loc_18010DFF3
0x18010df1e  cmp     [rsp+290h+var_270], 0Ah
0x18010df23  jz      loc_18010DFF3
0x18010df29  mov     r8, [rsp+290h+ppszPath]
0x18010df2e  lea     rdx, aSLogmanExeUpda; "\"%s\\logman.exe\" update WiFiSession -"...
0x18010df35  lea     rcx, [rsp+290h+var_258]
0x18010df3a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18010df3f  mov     ebx, eax
0x18010df41  test    eax, eax
0x18010df43  jns     short loc_18010DF4F
0x18010df45  mov     edx, 789h
0x18010df4a  jmp     loc_18010E014
0x18010df4f  mov     rdx, [rsp+290h+ppszPath]
0x18010df54  lea     rcx, [rsp+290h+var_240]
0x18010df59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010df5e  nop
0x18010df5f  lea     rdx, aLogfilesWmiWif; "\\logfiles\\wmi\\WiFi.etl"
0x18010df66  lea     rcx, [rsp+290h+var_240]
0x18010df6b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010df70  lea     rcx, [rsp+290h+var_240]
0x18010df75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010df7a  mov     r8, rax; pszMore
0x18010df7d  mov     edx, 104h; cchPath
0x18010df82  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18010df87  call    cs:__imp_PathCchAppend
0x18010df8d  mov     ebx, eax
0x18010df8f  test    eax, eax
0x18010df91  jns     short loc_18010DFBE
0x18010df93  mov     rcx, [rbp+198h]; this
0x18010df9a  mov     r9d, eax; char *
0x18010df9d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010dfa4  mov     edx, 78Dh; void *
0x18010dfa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010dfae  nop
0x18010dfaf  lea     rcx, [rsp+290h+var_240]
0x18010dfb4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010dfb9  jmp     loc_18010E066
0x18010dfbe  lea     rcx, [rsp+290h+var_240]
0x18010dfc3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010dfc8  lea     rcx, aCollectingWifi; "Collecting Wifi Session information.  T"...
0x18010dfcf  call    wprintf
0x18010dfd4  lea     r8, [rsp+290h+pszPath]; unsigned __int16 *
0x18010dfd9  mov     rdx, [rsp+290h+var_258]; unsigned __int16 *
0x18010dfde  mov     rcx, rdi; this
0x18010dfe1  call    ?UpdateWifiEtl@MdmLogCollector@@AEAAJPEAGPEBG@Z; MdmLogCollector::UpdateWifiEtl(ushort *,ushort const *)
0x18010dfe6  mov     ebx, eax
0x18010dfe8  test    eax, eax
0x18010dfea  jns     short loc_18010E064
0x18010dfec  mov     edx, 791h
0x18010dff1  jmp     short loc_18010E014
0x18010dff3  mov     r8, [rsp+290h+ppszPath]
0x18010dff8  lea     rdx, aSTracelogExeCa; "\"%s\\tracelog.exe\" -capturestate -sys"...
0x18010dfff  lea     rcx, [rsp+290h+var_258]
0x18010e004  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18010e009  mov     ebx, eax
0x18010e00b  test    eax, eax
0x18010e00d  jns     short loc_18010E02C
0x18010e00f  mov     edx, 77Fh; void *
0x18010e014  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e01b  mov     r9d, eax; char *
0x18010e01e  mov     rcx, [rbp+198h]; this
0x18010e025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e02a  jmp     short loc_18010E066
0x18010e02c  mov     r8d, 104h; nSize
0x18010e032  lea     rdx, [rsp+290h+pszPath]; lpDst
0x18010e037  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\systemdata\\etw\\WiFi.et"...
0x18010e03e  call    cs:__imp_ExpandEnvironmentStringsW
0x18010e044  test    eax, eax
0x18010e046  jnz     short loc_18010DFC8
0x18010e048  mov     rcx, [rbp+198h]; this
0x18010e04f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e056  mov     edx, 782h; void *
0x18010e05b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010e060  mov     ebx, eax
0x18010e062  jmp     short loc_18010E066
0x18010e064  xor     ebx, ebx
0x18010e066  lea     rcx, [rsp+290h+var_258]
0x18010e06b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010e070  mov     eax, ebx
0x18010e072  mov     rcx, [rbp+190h+var_10]
0x18010e079  xor     rcx, rsp; StackCookie
0x18010e07c  call    __security_check_cookie
0x18010e081  lea     r11, [rsp+290h+var_s0]
0x18010e089  mov     rbx, [r11+18h]
0x18010e08d  mov     rdi, [r11+20h]
0x18010e091  mov     rsp, r11
0x18010e094  pop     rbp
0x18010e095  retn
```
