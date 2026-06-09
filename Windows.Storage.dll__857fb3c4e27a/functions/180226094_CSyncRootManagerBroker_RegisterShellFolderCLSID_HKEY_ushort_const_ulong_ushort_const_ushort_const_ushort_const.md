# CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180226094`
- end: `0x1802265f5`
- name: `?RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z`
- size: `1377`
- prototype: `void(CSyncRootManagerBroker *__hidden this, HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802254b0`

## callees

- `0x18001c14c`
- `0x18004a030`
- `0x180120884`
- `0x180226094`
- `0x18035d160`
- `0x1803a4cb0`
- `0x1804db6b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226215`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226259`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226435`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18022654c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226215`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226259`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226435`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180226508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18022654c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226578`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226578`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180226598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802265c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180226113`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802261a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802262b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180226347`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802263f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802264c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180226113`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802261a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802262b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180226347`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802263f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802264c4`

## string_xrefs

- `0x180226387`: `CLSID`
- `0x18022645b`: `TargetFolderPath`
- `0x1802262db`: `%SystemRoot%\system32\shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSyncRootManagerBroker::RegisterShellFolderCLSID(
        CSyncRootManagerBroker *this,
        HKEY a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  REGSAM samDesired; // esi
  unsigned int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionse; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsh; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsi; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsj; // [rsp+20h] [rbp-61h]
  unsigned int dwOptionsk; // [rsp+20h] [rbp-61h]
  HKEY hKey; // [rsp+50h] [rbp-31h] BYREF
  HKEY v43; // [rsp+58h] [rbp-29h] BYREF
  HKEY v44; // [rsp+60h] [rbp-21h] BYREF
  HKEY v45; // [rsp+68h] [rbp-19h] BYREF
  HKEY v46; // [rsp+70h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  samDesired = a4 | 0x20006;
  v11 = RegCreateKeyExW(a2, a3, 0, 0, 0, samDesired, 0, &hKey, 0);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5EA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v11,
      dwOptions);
  v12 = SHRegSetString(hKey, 0, 0, a5);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5EC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v12,
      dwOptions);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v13 = RegCreateKeyExW(hKey, L"DefaultIcon", 0, 0, 0, samDesired, 0, &phkResult, 0);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5EF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v13,
      dwOptionsa);
  v15 = SHRegSetExpandStringW(phkResult, v14, 0, a6);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v15,
      dwOptionsa);
  v16 = RegSetValueExW(
          hKey,
          L"System.IsPinnedToNamespaceTree",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::pinnedState,
          4u);
  if ( v16 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v16,
      dwOptionsb);
  v17 = RegSetValueExW(
          hKey,
          L"SortOrderIndex",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::sortOrder,
          4u);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F5,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v17,
      dwOptionsc);
  v46 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v46,
    0);
  v18 = RegCreateKeyExW(hKey, L"InProcServer32", 0, 0, 0, samDesired, 0, &v46, 0);
  if ( v18 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v18,
      dwOptionsd);
  v20 = SHRegSetExpandStringW(v46, v19, 0, L"%SystemRoot%\\system32\\shell32.dll");
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5FA,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v20,
      dwOptionsd);
  v45 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v45,
    0);
  v21 = RegCreateKeyExW(hKey, L"Instance", 0, 0, 0, samDesired, 0, &v45, 0);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5FD,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v21,
      dwOptionse);
  v22 = RegSetValueExW(v45, L"CLSID", 0, 1u, L"{0E5AAE11-A475-4c5b-AB00-C66DE400274E}", 0x4Cu);
  if ( v22 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v22,
      dwOptionsf);
  v44 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v44,
    0);
  v23 = RegCreateKeyExW(v45, L"InitPropertyBag", 0, 0, 0, samDesired, 0, &v44, 0);
  if ( v23 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x602,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v23,
      dwOptionsg);
  v24 = RegSetValueExW(
          v44,
          L"Attributes",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::attributes,
          4u);
  if ( v24 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x604,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v24,
      dwOptionsh);
  v26 = SHRegSetExpandStringW(v44, v25, L"TargetFolderPath", a7);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v26,
      dwOptionsh);
  v43 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v43,
    0);
  v27 = RegCreateKeyExW(hKey, L"ShellFolder", 0, 0, 0, samDesired, 0, &v43, 0);
  if ( v27 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x609,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v27,
      dwOptionsi);
  v28 = RegSetValueExW(
          v43,
          L"FolderValueFlags",
          0,
          4u,
          &`CSyncRootManagerBroker::RegisterShellFolderCLSID'::`2'::folderValueFlags,
          4u);
  if ( v28 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x60B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v28,
      dwOptionsj);
  v29 = RegSetValueExW(v43, L"Attributes", 0, 4u, "M", 4u);
  if ( v29 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x60D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)v29,
      dwOptionsk);
  if ( v43 )
    RegCloseKey(v43);
  if ( v44 )
    RegCloseKey(v44);
  if ( v45 )
    RegCloseKey(v45);
  if ( v46 )
    RegCloseKey(v46);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180226094  mov     [rsp-8+arg_0], rbx
0x180226099  push    rbp
0x18022609a  push    rsi
0x18022609b  push    rdi
0x18022609c  push    r12
0x18022609e  push    r13
0x1802260a0  push    r14
0x1802260a2  push    r15
0x1802260a4  lea     rbp, [rsp-0Fh]
0x1802260a9  sub     rsp, 90h
0x1802260b0  mov     rax, cs:__security_cookie
0x1802260b7  xor     rax, rsp
0x1802260ba  mov     [rbp+3Fh+var_40], rax
0x1802260be  mov     esi, r9d
0x1802260c1  mov     rdi, r8
0x1802260c4  mov     rbx, rdx
0x1802260c7  mov     r14, [rbp+3Fh+arg_20]
0x1802260cb  mov     r15, [rbp+3Fh+arg_28]
0x1802260cf  mov     r12, [rbp+3Fh+arg_30]
0x1802260d3  xor     r13d, r13d
0x1802260d6  mov     [rbp+3Fh+hKey], r13
0x1802260da  xor     edx, edx
0x1802260dc  lea     rcx, [rbp+3Fh+hKey]
0x1802260e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1802260e5  or      esi, 20006h
0x1802260eb  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x1802260f0  lea     rax, [rbp+3Fh+hKey]
0x1802260f4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1802260f9  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1802260fe  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180226102  mov     [rsp+0C0h+dwOptions], r13d; int
0x180226107  xor     r9d, r9d; lpClass
0x18022610a  xor     r8d, r8d; Reserved
0x18022610d  mov     rdx, rdi; lpSubKey
0x180226110  mov     rcx, rbx; hKey
0x180226113  call    cs:__imp_RegCreateKeyExW
0x180226119  mov     rcx, [rbp+47h]; this
0x18022611d  test    eax, eax
0x18022611f  jz      short loc_180226136
0x180226121  mov     r9d, eax; char *
0x180226124  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18022612b  mov     edx, 5EAh; void *
0x180226130  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180226136  mov     r9, r14; unsigned __int16 *
0x180226139  xor     r8d, r8d; unsigned __int16 *
0x18022613c  xor     edx, edx; unsigned __int16 *
0x18022613e  mov     rcx, [rbp+3Fh+hKey]; HKEY
0x180226142  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180226147  mov     rcx, [rbp+47h]; this
0x18022614b  test    eax, eax
0x18022614d  jns     short loc_180226164
0x18022614f  mov     r9d, eax; char *
0x180226152  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226159  mov     edx, 5ECh; void *
0x18022615e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180226164  mov     [rbp+3Fh+var_48], r13
0x180226168  xor     edx, edx
0x18022616a  lea     rcx, [rbp+3Fh+var_48]
0x18022616e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180226173  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180226178  lea     rax, [rbp+3Fh+var_48]
0x18022617c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180226181  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180226186  mov     [rsp+0C0h+samDesired], esi; samDesired
0x18022618a  mov     [rsp+0C0h+dwOptions], r13d; int
0x18022618f  xor     r9d, r9d; lpClass
0x180226192  xor     r8d, r8d; Reserved
0x180226195  lea     rdx, aDefaulticon; "DefaultIcon"
0x18022619c  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1802261a0  call    cs:__imp_RegCreateKeyExW
0x1802261a6  mov     rcx, [rbp+47h]; this
0x1802261aa  test    eax, eax
0x1802261ac  jz      short loc_1802261C3
0x1802261ae  mov     r9d, eax; char *
0x1802261b1  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802261b8  mov     edx, 5EFh; void *
0x1802261bd  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1802261c3  mov     r9, r15
0x1802261c6  xor     r8d, r8d
0x1802261c9  mov     rcx, [rbp+3Fh+var_48]
0x1802261cd  call    SHRegSetExpandStringW
0x1802261d2  mov     rcx, [rbp+47h]; this
0x1802261d6  test    eax, eax
0x1802261d8  jns     short loc_1802261EF
0x1802261da  mov     r9d, eax; char *
0x1802261dd  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802261e4  mov     edx, 5F0h; void *
0x1802261e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802261ef  mov     ebx, 4
0x1802261f4  mov     [rsp+0C0h+samDesired], ebx; cbData
0x1802261f8  lea     rax, ?pinnedState@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::pinnedState
0x1802261ff  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180226204  mov     r9d, ebx; dwType
0x180226207  xor     r8d, r8d; Reserved
0x18022620a  lea     rdx, aSystemIspinned; "System.IsPinnedToNamespaceTree"
0x180226211  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180226215  call    cs:__imp_RegSetValueExW
0x18022621b  mov     rcx, [rbp+47h]; this
0x18022621f  test    eax, eax
0x180226221  jz      short loc_180226238
0x180226223  mov     r9d, eax; char *
0x180226226  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18022622d  mov     edx, 5F3h; void *
0x180226232  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180226238  mov     [rsp+0C0h+samDesired], ebx; cbData
0x18022623c  lea     rax, ?sortOrder@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::sortOrder
0x180226243  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x180226248  mov     r9d, ebx; dwType
0x18022624b  xor     r8d, r8d; Reserved
0x18022624e  lea     rdx, aSortorderindex; "SortOrderIndex"
0x180226255  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180226259  call    cs:__imp_RegSetValueExW
0x18022625f  mov     rcx, [rbp+47h]; this
0x180226263  test    eax, eax
0x180226265  jz      short loc_18022627C
0x180226267  mov     r9d, eax; char *
0x18022626a  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226271  mov     edx, 5F5h; void *
0x180226276  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18022627c  mov     [rbp+3Fh+var_50], r13
0x180226280  xor     edx, edx
0x180226282  lea     rcx, [rbp+3Fh+var_50]
0x180226286  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18022628b  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x180226290  lea     rax, [rbp+3Fh+var_50]
0x180226294  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180226299  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18022629e  mov     [rsp+0C0h+samDesired], esi; samDesired
0x1802262a2  mov     [rsp+0C0h+dwOptions], r13d; int
0x1802262a7  xor     r9d, r9d; lpClass
0x1802262aa  xor     r8d, r8d; Reserved
0x1802262ad  lea     rdx, aInprocserver32_0; "InProcServer32"
0x1802262b4  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1802262b8  call    cs:__imp_RegCreateKeyExW
0x1802262be  mov     rcx, [rbp+47h]; this
0x1802262c2  test    eax, eax
0x1802262c4  jz      short loc_1802262DB
0x1802262c6  mov     r9d, eax; char *
0x1802262c9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802262d0  mov     edx, 5F8h; void *
0x1802262d5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1802262db  lea     r9, aSystemrootSyst_1; "%SystemRoot%\\system32\\shell32.dll"
0x1802262e2  xor     r8d, r8d
0x1802262e5  mov     rcx, [rbp+3Fh+var_50]
0x1802262e9  call    SHRegSetExpandStringW
0x1802262ee  mov     rcx, [rbp+47h]; this
0x1802262f2  test    eax, eax
0x1802262f4  jns     short loc_18022630B
0x1802262f6  mov     r9d, eax; char *
0x1802262f9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226300  mov     edx, 5FAh; void *
0x180226305  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18022630b  mov     [rbp+3Fh+var_58], r13
0x18022630f  xor     edx, edx
0x180226311  lea     rcx, [rbp+3Fh+var_58]
0x180226315  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18022631a  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x18022631f  lea     rax, [rbp+3Fh+var_58]
0x180226323  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180226328  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18022632d  mov     [rsp+0C0h+samDesired], esi; samDesired
0x180226331  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x180226336  xor     r9d, r9d; lpClass
0x180226339  xor     r8d, r8d; Reserved
0x18022633c  lea     rdx, aInstance; "Instance"
0x180226343  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180226347  call    cs:__imp_RegCreateKeyExW
0x18022634d  mov     rcx, [rbp+47h]; this
0x180226351  test    eax, eax
0x180226353  jz      short loc_18022636A
0x180226355  mov     r9d, eax; char *
0x180226358  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18022635f  mov     edx, 5FDh; void *
0x180226364  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18022636a  mov     [rsp+0C0h+samDesired], 4Ch ; 'L'; cbData
0x180226372  lea     rax, Data; "{0E5AAE11-A475-4c5b-AB00-C66DE400274E}"
0x180226379  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x18022637e  mov     r9d, 1; dwType
0x180226384  xor     r8d, r8d; Reserved
0x180226387  lea     rdx, aClsid_3; "CLSID"
0x18022638e  mov     rcx, [rbp+3Fh+var_58]; hKey
0x180226392  call    cs:__imp_RegSetValueExW
0x180226398  mov     rcx, [rbp+47h]; this
0x18022639c  test    eax, eax
0x18022639e  jz      short loc_1802263B5
0x1802263a0  mov     r9d, eax; char *
0x1802263a3  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802263aa  mov     edx, 5FFh; void *
0x1802263af  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1802263b5  mov     [rbp+3Fh+var_60], r13
0x1802263b9  xor     edx, edx
0x1802263bb  lea     rcx, [rbp+3Fh+var_60]
0x1802263bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1802263c4  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x1802263c9  lea     rax, [rbp+3Fh+var_60]
0x1802263cd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1802263d2  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1802263d7  mov     [rsp+0C0h+samDesired], esi; samDesired
0x1802263db  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x1802263e0  xor     r9d, r9d; lpClass
0x1802263e3  xor     r8d, r8d; Reserved
0x1802263e6  lea     rdx, aInitpropertyba; "InitPropertyBag"
0x1802263ed  mov     rcx, [rbp+3Fh+var_58]; hKey
0x1802263f1  call    cs:__imp_RegCreateKeyExW
0x1802263f7  mov     rcx, [rbp+47h]; this
0x1802263fb  test    eax, eax
0x1802263fd  jz      short loc_180226414
0x1802263ff  mov     r9d, eax; char *
0x180226402  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226409  mov     edx, 602h; void *
0x18022640e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180226414  mov     [rsp+0C0h+samDesired], ebx; cbData
0x180226418  lea     rax, ?attributes@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::attributes
0x18022641f  mov     qword ptr [rsp+0C0h+dwOptions], rax; int
0x180226424  mov     r9d, ebx; dwType
0x180226427  xor     r8d, r8d; Reserved
0x18022642a  lea     rdx, aAttributes; "Attributes"
0x180226431  mov     rcx, [rbp+3Fh+var_60]; hKey
0x180226435  call    cs:__imp_RegSetValueExW
0x18022643b  mov     rcx, [rbp+47h]; this
0x18022643f  test    eax, eax
0x180226441  jz      short loc_180226458
0x180226443  mov     r9d, eax; char *
0x180226446  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18022644d  mov     edx, 604h; void *
0x180226452  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180226458  mov     r9, r12
0x18022645b  lea     r8, aTargetfolderpa; "TargetFolderPath"
0x180226462  mov     rcx, [rbp+3Fh+var_60]
0x180226466  call    SHRegSetExpandStringW
0x18022646b  mov     rcx, [rbp+47h]; this
0x18022646f  test    eax, eax
0x180226471  jns     short loc_180226488
0x180226473  mov     r9d, eax; char *
0x180226476  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18022647d  mov     edx, 606h; void *
0x180226482  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180226488  mov     [rbp+3Fh+var_68], r13
0x18022648c  xor     edx, edx
0x18022648e  lea     rcx, [rbp+3Fh+var_68]
0x180226492  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180226497  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x18022649c  lea     rax, [rbp+3Fh+var_68]
0x1802264a0  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1802264a5  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1802264aa  mov     [rsp+0C0h+samDesired], esi; samDesired
0x1802264ae  mov     [rsp+0C0h+dwOptions], r13d; unsigned int
0x1802264b3  xor     r9d, r9d; lpClass
0x1802264b6  xor     r8d, r8d; Reserved
0x1802264b9  lea     rdx, aShellfolder; "ShellFolder"
0x1802264c0  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1802264c4  call    cs:__imp_RegCreateKeyExW
0x1802264ca  mov     rcx, [rbp+47h]; this
0x1802264ce  test    eax, eax
0x1802264d0  jz      short loc_1802264E7
0x1802264d2  mov     r9d, eax; char *
0x1802264d5  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802264dc  mov     edx, 609h; void *
0x1802264e1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1802264e7  mov     [rsp+0C0h+samDesired], ebx; cbData
0x1802264eb  lea     rax, ?folderValueFlags@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; ulong const `CSyncRootManagerBroker::RegisterShellFolderCLSID(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,ushort const *)'::`2'::folderValueFlags
0x1802264f2  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x1802264f7  mov     r9d, ebx; dwType
0x1802264fa  xor     r8d, r8d; Reserved
0x1802264fd  lea     rdx, aFoldervaluefla; "FolderValueFlags"
0x180226504  mov     rcx, [rbp+3Fh+var_68]; hKey
0x180226508  call    cs:__imp_RegSetValueExW
0x18022650e  mov     rcx, [rbp+47h]; this
0x180226512  test    eax, eax
0x180226514  jz      short loc_18022652B
0x180226516  mov     r9d, eax; char *
0x180226519  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226520  mov     edx, 60Bh; void *
0x180226525  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18022652b  mov     [rsp+0C0h+samDesired], ebx; cbData
0x18022652f  lea     rax, ?folderAttributes@?1??RegisterShellFolderCLSID@CSyncRootManagerBroker@@AEAAXPEAUHKEY__@@PEBGK111@Z@4KB; "M"
0x180226536  mov     qword ptr [rsp+0C0h+dwOptions], rax; unsigned int
0x18022653b  mov     r9d, ebx; dwType
0x18022653e  xor     r8d, r8d; Reserved
0x180226541  lea     rdx, aAttributes; "Attributes"
0x180226548  mov     rcx, [rbp+3Fh+var_68]; hKey
0x18022654c  call    cs:__imp_RegSetValueExW
0x180226552  mov     rcx, [rbp+47h]; this
0x180226556  test    eax, eax
0x180226558  jz      short loc_18022656F
0x18022655a  mov     r9d, eax; char *
0x18022655d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180226564  mov     edx, 60Dh; void *
0x180226569  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18022656f  mov     rcx, [rbp+3Fh+var_68]; hKey
0x180226573  test    rcx, rcx
0x180226576  jz      short loc_18022657F
0x180226578  call    cs:__imp_RegCloseKey
0x18022657e  nop
0x18022657f  mov     rcx, [rbp+3Fh+var_60]; hKey
0x180226583  test    rcx, rcx
0x180226586  jz      short loc_18022658F
0x180226588  call    cs:__imp_RegCloseKey
0x18022658e  nop
0x18022658f  mov     rcx, [rbp+3Fh+var_58]; hKey
  ... truncated ...
```
