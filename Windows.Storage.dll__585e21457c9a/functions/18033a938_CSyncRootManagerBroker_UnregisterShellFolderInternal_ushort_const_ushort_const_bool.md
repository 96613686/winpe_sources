# CSyncRootManagerBroker::UnregisterShellFolderInternal(ushort const *,ushort const *,bool *)

- ea: `0x18033a938`
- end: `0x18033ad71`
- name: `?UnregisterShellFolderInternal@CSyncRootManagerBroker@@AEAAJPEBG0PEA_N@Z`
- size: `1081`
- prototype: `int(CSyncRootManagerBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802254b0`
- `0x180339ca0`
- `0x180560360`

## callees

- `0x18001b340`
- `0x18001c14c`
- `0x180039ee0`
- `0x18004a030`
- `0x1800586b0`
- `0x1800dd190`
- `0x1801158c0`
- `0x180226924`
- `0x18033a938`
- `0x18033c28c`
- `0x1803a4cb0`
- `0x1804db6b4`
- `0x18055e214`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18033ab21`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18033ab21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18033aae2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18033aae2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033abe9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033ac40`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033acde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033abe9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033ac40`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18033acde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033ad1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033ad3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033ad1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033ad3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18033ab72`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18033ac99`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18033ab72`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18033ac99`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18033a9ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18033a9ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ab33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ab4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ad2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ab33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ab4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033ad2e`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18033ac7d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18033ac7d`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryInfoKeyW` at `0x18033aa36`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryInfoKeyW` at `0x18033aa36`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18033aaa0`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18033aaa0`

## string_xrefs

- `0x18033abef`: `Software\Classes\CLSID\`
- `0x18033aafc`: `NamespaceCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CSyncRootManagerBroker::UnregisterShellFolderInternal(
        CSyncRootManagerBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  const unsigned __int16 **v7; // rdx
  int SyncRootManagerRegistryLocation; // eax
  unsigned int v9; // eax
  LSTATUS v10; // eax
  DWORD v11; // esi
  __int64 v12; // rdi
  LSTATUS v13; // eax
  int v14; // r9d
  int v15; // eax
  WCHAR *v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // r8
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rdx
  const WCHAR *v21; // rdx
  unsigned int v22; // eax
  const WCHAR *v23; // rdx
  int dwOptions; // [rsp+20h] [rbp-108h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-108h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-108h]
  unsigned int *samDesired; // [rsp+28h] [rbp-100h]
  DWORD pcchMaxSubKeyLen; // [rsp+50h] [rbp-D8h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-D0h] BYREF
  DWORD pcchName[2]; // [rsp+60h] [rbp-C8h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-C0h] BYREF
  DWORD pcSubKeys; // [rsp+70h] [rbp-B8h] BYREF
  LPWSTR pszName; // [rsp+78h] [rbp-B0h] BYREF
  LPCWSTR v35[3]; // [rsp+80h] [rbp-A8h] BYREF
  unsigned __int64 v36; // [rsp+98h] [rbp-90h]
  LPCWSTR Src[4]; // [rsp+A0h] [rbp-88h] BYREF
  LPCWSTR pszSubKey[4]; // [rsp+C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  lpSubKey = a2;
  CloudFilesTelemetry::UnregisterShellFolder<unsigned short const * &>(&lpSubKey);
  *a4 = 0;
  lpSubKey = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                      v7);
  if ( SyncRootManagerRegistryLocation < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)SyncRootManagerRegistryLocation,
      dwOptions);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20119u, 0, &hkey, 0);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x57F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v9,
      dwOptionsa);
  pcSubKeys = 0;
  pcchMaxSubKeyLen = 0;
  v10 = SHQueryInfoKeyW(hkey, &pcSubKeys, &pcchMaxSubKeyLen, 0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x583,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsb);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pszName,
    0,
    ++pcchMaxSubKeyLen);
  v11 = 0;
  v12 = -1;
  while ( v11 < pcSubKeys )
  {
    pcchName[0] = pcchMaxSubKeyLen;
    v13 = SHEnumKeyExW(hkey, v11, pszName, pcchName);
    if ( v13 >= 0 )
    {
      if ( !a3 || CompareStringOrdinal(pszName, -1, a3, -1, 1) != 2 )
      {
        lpSubKey = 0;
        v15 = SHRegAllocData(hkey, pszName, L"NamespaceCLSID", v14, (void **)&lpSubKey, samDesired);
        v16 = (WCHAR *)lpSubKey;
        if ( v15 >= 0 && !(unsigned int)_o__wcsicmp(a2, lpSubKey) )
        {
          if ( v16 )
            CoTaskMemFree(v16);
          goto LABEL_38;
        }
        if ( v16 )
          CoTaskMemFree(v16);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v13,
        dwOptionsb);
    }
    ++v11;
  }
  *(_QWORD *)pcchName = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    pcchName,
    0);
  v17 = RegOpenCurrentUser(0xF013Fu, (PHKEY)pcchName);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v17,
      dwOptionsb);
  std::wstring::wstring(Src, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Desktop\\Namespace\\");
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  std::wstring::_Append<unsigned short>(Src);
  v19 = (const WCHAR *)Src;
  if ( Src[3] > (LPCWSTR)7 )
    v19 = Src[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v19);
  std::wstring::wstring(v35, L"Software\\Classes\\CLSID\\");
  do
    ++v12;
  while ( a2[v12] );
  std::wstring::_Append<unsigned short>(v35);
  v20 = (const WCHAR *)v35;
  if ( v36 > 7 )
    v20 = v35[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v20);
  std::wstring::wstring(
    pszSubKey,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\HideDesktopIcons\\NewStartPanel");
  v21 = (const WCHAR *)pszSubKey;
  if ( pszSubKey[3] > (LPCWSTR)7 )
    v21 = pszSubKey[0];
  SHDeleteValueW(*(HKEY *)pcchName, v21, a2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    pcchName,
    0);
  v22 = RegOpenCurrentUser(0xF023Fu, (PHKEY)pcchName);
  if ( v22 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5AF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v22,
      dwOptionsb);
  v23 = (const WCHAR *)v35;
  if ( v36 > 7 )
    v23 = v35[0];
  RegDeleteTreeW(*(HKEY *)pcchName, v23);
  *a4 = 1;
  std::pair<std::wstring,int>::~pair<std::wstring,int>(pszSubKey);
  std::pair<std::wstring,int>::~pair<std::wstring,int>(v35);
  std::pair<std::wstring,int>::~pair<std::wstring,int>(Src);
  if ( *(_QWORD *)pcchName )
    RegCloseKey(*(HKEY *)pcchName);
LABEL_38:
  if ( pszName )
    CoTaskMemFree(pszName);
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x18033a938  push    rbx
0x18033a93a  push    rsi
0x18033a93b  push    rdi
0x18033a93c  push    r12
0x18033a93e  push    r13
0x18033a940  push    r14
0x18033a942  push    r15
0x18033a944  sub     rsp, 0F0h
0x18033a94b  mov     rax, cs:__security_cookie
0x18033a952  xor     rax, rsp
0x18033a955  mov     [rsp+128h+var_48], rax
0x18033a95d  mov     r12, r9
0x18033a960  mov     r15, r8
0x18033a963  mov     r14, rdx
0x18033a966  mov     [rsp+128h+lpSubKey], rdx
0x18033a96b  xor     r13d, r13d
0x18033a96e  lea     rcx, [rsp+128h+lpSubKey]
0x18033a973  call    ??$UnregisterShellFolder@AEAPEBG@CloudFilesTelemetry@@SAXAEAPEBG@Z; CloudFilesTelemetry::UnregisterShellFolder<ushort const * &>(ushort const * &)
0x18033a978  mov     [r12], r13b
0x18033a97c  mov     [rsp+128h+lpSubKey], r13
0x18033a981  lea     rcx, [rsp+128h+lpSubKey]; this
0x18033a986  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x18033a98b  mov     rcx, [rsp+128h]; this
0x18033a993  test    eax, eax
0x18033a995  jns     short loc_18033A9AB
0x18033a997  mov     r9d, eax; char *
0x18033a99a  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033a9a1  mov     edx, 57Dh; void *
0x18033a9a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18033a9ab  mov     [rsp+128h+hkey], r13
0x18033a9b0  xor     edx, edx
0x18033a9b2  lea     rcx, [rsp+128h+hkey]
0x18033a9b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18033a9bc  mov     [rsp+128h+lpdwDisposition], r13; lpdwDisposition
0x18033a9c1  lea     rax, [rsp+128h+hkey]
0x18033a9c6  mov     [rsp+128h+phkResult], rax; phkResult
0x18033a9cb  mov     [rsp+128h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18033a9d0  mov     dword ptr [rsp+128h+samDesired], 20119h; unsigned int *
0x18033a9d8  mov     [rsp+128h+dwOptions], r13d; unsigned int
0x18033a9dd  xor     r9d, r9d; lpClass
0x18033a9e0  xor     r8d, r8d; Reserved
0x18033a9e3  mov     rdx, [rsp+128h+lpSubKey]; lpSubKey
0x18033a9e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18033a9ef  call    cs:__imp_RegCreateKeyExW
0x18033a9f5  mov     rcx, [rsp+128h]; this
0x18033a9fd  test    eax, eax
0x18033a9ff  jz      short loc_18033AA15
0x18033aa01  mov     r9d, eax; char *
0x18033aa04  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033aa0b  mov     edx, 57Fh; void *
0x18033aa10  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18033aa15  mov     [rsp+128h+pcSubKeys], r13d
0x18033aa1a  mov     [rsp+128h+pcchMaxSubKeyLen], r13d
0x18033aa1f  mov     qword ptr [rsp+128h+dwOptions], r13; unsigned int
0x18033aa24  xor     r9d, r9d; pcValues
0x18033aa27  lea     r8, [rsp+128h+pcchMaxSubKeyLen]; pcchMaxSubKeyLen
0x18033aa2c  lea     rdx, [rsp+128h+pcSubKeys]; pcSubKeys
0x18033aa31  mov     rcx, [rsp+128h+hkey]; hkey
0x18033aa36  call    cs:__imp_SHQueryInfoKeyW
0x18033aa3c  mov     rcx, [rsp+128h]; this
0x18033aa44  test    eax, eax
0x18033aa46  jns     short loc_18033AA5C
0x18033aa48  mov     r9d, eax; char *
0x18033aa4b  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033aa52  mov     edx, 583h; void *
0x18033aa57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18033aa5c  mov     eax, [rsp+128h+pcchMaxSubKeyLen]
0x18033aa60  inc     eax
0x18033aa62  mov     [rsp+128h+pcchMaxSubKeyLen], eax
0x18033aa66  mov     r8d, eax
0x18033aa69  xor     edx, edx
0x18033aa6b  lea     rcx, [rsp+128h+pszName]
0x18033aa70  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18033aa75  nop
0x18033aa76  mov     esi, r13d
0x18033aa79  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18033aa7d  cmp     esi, [rsp+128h+pcSubKeys]
0x18033aa81  jnb     loc_18033AB57
0x18033aa87  mov     eax, [rsp+128h+pcchMaxSubKeyLen]
0x18033aa8b  mov     [rsp+128h+pcchName], eax
0x18033aa8f  lea     r9, [rsp+128h+pcchName]; pcchName
0x18033aa94  mov     r8, [rsp+128h+pszName]; pszName
0x18033aa99  mov     edx, esi; dwIndex
0x18033aa9b  mov     rcx, [rsp+128h+hkey]; hkey
0x18033aaa0  call    cs:__imp_SHEnumKeyExW
0x18033aaa6  mov     rcx, [rsp+128h]; this
0x18033aaae  test    eax, eax
0x18033aab0  jns     short loc_18033AAC8
0x18033aab2  mov     r9d, eax; char *
0x18033aab5  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033aabc  mov     edx, 58Ch; void *
0x18033aac1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033aac6  jmp     short loc_18033AB39
0x18033aac8  test    r15, r15
0x18033aacb  jz      short loc_18033AAED
0x18033aacd  mov     [rsp+128h+dwOptions], 1; bIgnoreCase
0x18033aad5  mov     r9d, edi; cchCount2
0x18033aad8  mov     r8, r15; lpString2
0x18033aadb  mov     edx, edi; cchCount1
0x18033aadd  mov     rcx, [rsp+128h+pszName]; lpString1
0x18033aae2  call    cs:__imp_CompareStringOrdinal
0x18033aae8  cmp     eax, 2
0x18033aaeb  jz      short loc_18033AB39
0x18033aaed  mov     [rsp+128h+lpSubKey], r13
0x18033aaf2  lea     rax, [rsp+128h+lpSubKey]
0x18033aaf7  mov     qword ptr [rsp+128h+dwOptions], rax; void **
0x18033aafc  lea     r8, aNamespaceclsid; "NamespaceCLSID"
0x18033ab03  mov     rdx, [rsp+128h+pszName]; unsigned __int16 *
0x18033ab08  mov     rcx, [rsp+128h+hkey]; HKEY
0x18033ab0d  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18033ab12  mov     rbx, [rsp+128h+lpSubKey]
0x18033ab17  test    eax, eax
0x18033ab19  js      short loc_18033AB2B
0x18033ab1b  mov     rdx, rbx
0x18033ab1e  mov     rcx, r14
0x18033ab21  call    cs:__imp__o__wcsicmp
0x18033ab27  test    eax, eax
0x18033ab29  jz      short loc_18033AB40
0x18033ab2b  test    rbx, rbx
0x18033ab2e  jz      short loc_18033AB39
0x18033ab30  mov     rcx, rbx; pv
0x18033ab33  call    cs:__imp_CoTaskMemFree
0x18033ab39  inc     esi
0x18033ab3b  jmp     loc_18033AA7D
0x18033ab40  test    rbx, rbx
0x18033ab43  jz      loc_18033AD24
0x18033ab49  mov     rcx, rbx; pv
0x18033ab4c  call    cs:__imp_CoTaskMemFree
0x18033ab52  jmp     loc_18033AD24
0x18033ab57  mov     qword ptr [rsp+128h+pcchName], r13
0x18033ab5c  xor     edx, edx
0x18033ab5e  lea     rcx, [rsp+128h+pcchName]
0x18033ab63  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18033ab68  lea     rdx, [rsp+128h+pcchName]; phkResult
0x18033ab6d  mov     ecx, 0F013Fh; samDesired
0x18033ab72  call    cs:__imp_RegOpenCurrentUser
0x18033ab78  mov     rcx, [rsp+128h]; this
0x18033ab80  test    eax, eax
0x18033ab82  jz      short loc_18033AB98
0x18033ab84  mov     r9d, eax; char *
0x18033ab87  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033ab8e  mov     edx, 5A1h; void *
0x18033ab93  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18033ab98  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18033ab9f  lea     rcx, [rsp+128h+Src]
0x18033aba7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18033abac  nop
0x18033abad  mov     r8, rdi
0x18033abb0  inc     r8
0x18033abb3  cmp     [r14+r8*2], r13w
0x18033abb8  jnz     short loc_18033ABB0
0x18033abba  mov     rdx, r14
0x18033abbd  lea     rcx, [rsp+128h+Src]; Src
0x18033abc5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18033abca  lea     rdx, [rsp+128h+Src]
0x18033abd2  cmp     [rsp+128h+var_70], 7
0x18033abdb  cmova   rdx, [rsp+128h+Src]; lpSubKey
0x18033abe4  mov     rcx, qword ptr [rsp+128h+pcchName]; hKey
0x18033abe9  call    cs:__imp_RegDeleteTreeW
0x18033abef  lea     rdx, aSoftwareClasse_4; "Software\\Classes\\CLSID\\"
0x18033abf6  lea     rcx, [rsp+128h+var_A8]
0x18033abfe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18033ac03  nop
0x18033ac04  inc     rdi
0x18033ac07  cmp     [r14+rdi*2], r13w
0x18033ac0c  jnz     short loc_18033AC04
0x18033ac0e  mov     r8, rdi
0x18033ac11  mov     rdx, r14
0x18033ac14  lea     rcx, [rsp+128h+var_A8]; Src
0x18033ac1c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18033ac21  lea     rdx, [rsp+128h+var_A8]
0x18033ac29  cmp     [rsp+128h+var_90], 7
0x18033ac32  cmova   rdx, [rsp+128h+var_A8]; lpSubKey
0x18033ac3b  mov     rcx, qword ptr [rsp+128h+pcchName]; hKey
0x18033ac40  call    cs:__imp_RegDeleteTreeW
0x18033ac46  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18033ac4d  lea     rcx, [rsp+128h+pszSubKey]
0x18033ac55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18033ac5a  nop
0x18033ac5b  lea     rdx, [rsp+128h+pszSubKey]
0x18033ac63  cmp     [rsp+128h+var_50], 7
0x18033ac6c  cmova   rdx, [rsp+128h+pszSubKey]; pszSubKey
0x18033ac75  mov     r8, r14; pszValue
0x18033ac78  mov     rcx, qword ptr [rsp+128h+pcchName]; hkey
0x18033ac7d  call    cs:__imp_SHDeleteValueW
0x18033ac83  xor     edx, edx
0x18033ac85  lea     rcx, [rsp+128h+pcchName]
0x18033ac8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18033ac8f  lea     rdx, [rsp+128h+pcchName]; phkResult
0x18033ac94  mov     ecx, 0F023Fh; samDesired
0x18033ac99  call    cs:__imp_RegOpenCurrentUser
0x18033ac9f  mov     rcx, [rsp+128h]; this
0x18033aca7  test    eax, eax
0x18033aca9  jz      short loc_18033ACBF
0x18033acab  mov     r9d, eax; char *
0x18033acae  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18033acb5  mov     edx, 5AFh; void *
0x18033acba  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18033acbf  lea     rdx, [rsp+128h+var_A8]
0x18033acc7  cmp     [rsp+128h+var_90], 7
0x18033acd0  cmova   rdx, [rsp+128h+var_A8]; lpSubKey
0x18033acd9  mov     rcx, qword ptr [rsp+128h+pcchName]; hKey
0x18033acde  call    cs:__imp_RegDeleteTreeW
0x18033ace4  mov     byte ptr [r12], 1
0x18033ace9  lea     rcx, [rsp+128h+pszSubKey]; void *
0x18033acf1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18033acf6  nop
0x18033acf7  lea     rcx, [rsp+128h+var_A8]; void *
0x18033acff  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18033ad04  nop
0x18033ad05  lea     rcx, [rsp+128h+Src]; void *
0x18033ad0d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@QEAA@XZ; std::pair<std::wstring,int>::~pair<std::wstring,int>(void)
0x18033ad12  nop
0x18033ad13  mov     rcx, qword ptr [rsp+128h+pcchName]; hKey
0x18033ad18  test    rcx, rcx
0x18033ad1b  jz      short loc_18033AD24
0x18033ad1d  call    cs:__imp_RegCloseKey
0x18033ad23  nop
0x18033ad24  mov     rcx, [rsp+128h+pszName]; pv
0x18033ad29  test    rcx, rcx
0x18033ad2c  jz      short loc_18033AD35
0x18033ad2e  call    cs:__imp_CoTaskMemFree
0x18033ad34  nop
0x18033ad35  mov     rcx, [rsp+128h+hkey]; hKey
0x18033ad3a  test    rcx, rcx
0x18033ad3d  jz      short loc_18033AD45
0x18033ad3f  call    cs:__imp_RegCloseKey
0x18033ad45  xor     eax, eax
0x18033ad47  jmp     short loc_18033AD4D
0x18033ad49  mov     eax, [rsp+128h+pcchName]
0x18033ad4d  mov     rcx, [rsp+128h+var_48]
0x18033ad55  xor     rcx, rsp; StackCookie
0x18033ad58  call    __security_check_cookie
0x18033ad5d  add     rsp, 0F0h
0x18033ad64  pop     r15
0x18033ad66  pop     r14
0x18033ad68  pop     r13
0x18033ad6a  pop     r12
0x18033ad6c  pop     rdi
0x18033ad6d  pop     rsi
0x18033ad6e  pop     rbx
0x18033ad6f  retn
```
