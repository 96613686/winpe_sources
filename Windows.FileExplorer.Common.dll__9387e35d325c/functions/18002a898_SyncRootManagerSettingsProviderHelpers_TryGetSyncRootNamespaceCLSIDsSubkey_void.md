# SyncRootManagerSettingsProviderHelpers::TryGetSyncRootNamespaceCLSIDsSubkey(void *)

- ea: `0x18002a898`
- end: `0x18002aa2f`
- name: `?TryGetSyncRootNamespaceCLSIDsSubkey@SyncRootManagerSettingsProviderHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(PHKEY phkResult, PSID Sid)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a4e4`
- `0x18002a7d0`
- `0x18006e614`

## callees

- `0x180007900`
- `0x180015fa0`
- `0x180016440`
- `0x18001d320`
- `0x1800202c0`
- `0x18002037c`
- `0x18002a898`
- `0x18002aa38`
- `0x18002ab7c`
- `0x1800348e8`
- `0x180037780`
- `0x18006b7d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a9ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a9ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002a925`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002a925`

## string_xrefs

- `0x18002a95e`: `\NamespaceCLSIDs!`
- `0x18002a8e7`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x18002a92f`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x18002a9d3`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
PHKEY __fastcall SyncRootManagerSettingsProviderHelpers::TryGetSyncRootNamespaceCLSIDsSubkey(
        PHKEY phkResult,
        const unsigned __int16 **Sid)
{
  int SyncRootManagerRegistryLocation; // eax
  const char *v5; // r9
  __int64 v6; // rax
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  int phkResulta; // [rsp+20h] [rbp-79h]
  int phkResultb; // [rsp+20h] [rbp-79h]
  LPWSTR StringSid; // [rsp+30h] [rbp-69h] BYREF
  int v13; // [rsp+38h] [rbp-61h]
  _QWORD v14[2]; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v17[32]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v18[32]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v14[1] = phkResult;
  v13 = 0;
  v14[0] = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)v14,
                                      Sid);
  if ( SyncRootManagerRegistryLocation < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      (const char *)(unsigned int)SyncRootManagerRegistryLocation,
      phkResulta);
  std::wstring::wstring(v17, v14[0]);
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      v5);
  std::wstring::wstring(v16, StringSid);
  *phkResult = 0;
  v13 = 1;
  v6 = std::operator+<unsigned short>(v18, v17, L"\\NamespaceCLSIDs!");
  std::operator+<unsigned short>(lpSubKey, v6, v16);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v7 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v7 = lpSubKey[0];
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x2011Bu, phkResult);
  if ( (v8 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      (const char *)v8,
      phkResultb);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&StringSid);
  std::wstring::_Tidy_deallocate(v17);
  return phkResult;
}

```

## disassembly

```asm
0x18002a898  mov     [rsp-8+arg_10], rbx
0x18002a89d  push    rbp
0x18002a89e  push    rsi
0x18002a89f  push    rdi
0x18002a8a0  lea     rbp, [rsp-47h]
0x18002a8a5  sub     rsp, 0E0h
0x18002a8ac  mov     rax, cs:__security_cookie
0x18002a8b3  xor     rax, rsp
0x18002a8b6  mov     [rbp+57h+var_20], rax
0x18002a8ba  mov     rsi, rdx
0x18002a8bd  mov     rbx, rcx
0x18002a8c0  mov     [rbp+57h+var_A8], rcx
0x18002a8c4  mov     [rbp+57h+var_B8], 0
0x18002a8cb  mov     [rbp+57h+var_B0], 0
0x18002a8d3  lea     rcx, [rbp+57h+var_B0]; this
0x18002a8d7  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x18002a8dc  mov     rcx, [rbp+5Fh]; this
0x18002a8e0  test    eax, eax
0x18002a8e2  jns     short loc_18002A8F9
0x18002a8e4  mov     r9d, eax; char *
0x18002a8e7  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002a8ee  mov     edx, 71h ; 'q'; void *
0x18002a8f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a8f9  mov     rdx, [rbp+57h+var_B0]
0x18002a8fd  lea     rcx, [rbp+57h+var_60]
0x18002a901  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a906  nop
0x18002a907  mov     [rbp+57h+StringSid], 0
0x18002a90f  xor     edx, edx
0x18002a911  lea     rcx, [rbp+57h+StringSid]
0x18002a915  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a91a  mov     rdi, [rbp+5Fh]
0x18002a91e  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18002a922  mov     rcx, rsi; Sid
0x18002a925  call    cs:__imp_ConvertSidToStringSidW
0x18002a92b  test    eax, eax
0x18002a92d  jnz     short loc_18002A942
0x18002a92f  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002a936  lea     edx, [rax+75h]; void *
0x18002a939  mov     rcx, rdi; this
0x18002a93c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002a942  mov     rdx, [rbp+57h+StringSid]
0x18002a946  lea     rcx, [rbp+57h+var_80]
0x18002a94a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a94f  nop
0x18002a950  mov     qword ptr [rbx], 0
0x18002a957  mov     [rbp+57h+var_B8], 1
0x18002a95e  lea     r8, aNamespaceclsid_1; "\\NamespaceCLSIDs!"
0x18002a965  lea     rdx, [rbp+57h+var_60]
0x18002a969  lea     rcx, [rbp+57h+var_40]
0x18002a96d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002a972  nop
0x18002a973  lea     r8, [rbp+57h+var_80]
0x18002a977  mov     rdx, rax
0x18002a97a  lea     rcx, [rbp+57h+lpSubKey]
0x18002a97e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002a983  nop
0x18002a984  lea     rcx, [rbp+57h+var_40]
0x18002a988  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a98d  xor     edx, edx
0x18002a98f  mov     rcx, rbx
0x18002a992  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a997  lea     rdx, [rbp+57h+lpSubKey]
0x18002a99b  cmp     [rbp+57h+var_88], 7
0x18002a9a0  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002a9a5  mov     qword ptr [rsp+0F0h+phkResult], rbx; int
0x18002a9aa  mov     r9d, 2011Bh; samDesired
0x18002a9b0  xor     r8d, r8d; ulOptions
0x18002a9b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a9ba  call    cs:__imp_RegOpenKeyExW
0x18002a9c0  mov     r9d, eax; char *
0x18002a9c3  test    eax, 0FFFFFFFDh
0x18002a9c8  setnz   al
0x18002a9cb  mov     rcx, [rbp+5Fh]; this
0x18002a9cf  test    al, al
0x18002a9d1  jz      short loc_18002A9E5
0x18002a9d3  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18002a9da  mov     edx, 7Eh ; '~'; void *
0x18002a9df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a9e5  lea     rcx, [rbp+57h+lpSubKey]
0x18002a9e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9ee  nop
0x18002a9ef  lea     rcx, [rbp+57h+var_80]
0x18002a9f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9f8  nop
0x18002a9f9  lea     rcx, [rbp+57h+StringSid]; void *
0x18002a9fd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002aa02  nop
0x18002aa03  lea     rcx, [rbp+57h+var_60]
0x18002aa07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa0c  mov     rax, rbx
0x18002aa0f  mov     rcx, [rbp+57h+var_20]
0x18002aa13  xor     rcx, rsp; StackCookie
0x18002aa16  call    __security_check_cookie
0x18002aa1b  mov     rbx, [rsp+0F0h+arg_10]
0x18002aa23  add     rsp, 0E0h
0x18002aa2a  pop     rdi
0x18002aa2b  pop     rsi
0x18002aa2c  pop     rbp
0x18002aa2d  retn
```
