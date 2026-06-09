# Container::Manager::Core::Details::SpecializationLayer::InstallEdgeInternal(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800d9f2c`
- end: `0x1800dab6b`
- name: `?InstallEdgeInternal@SpecializationLayer@Details@Core@Manager@Container@@AEAAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z`
- size: `3135`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d9dc8`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180008bf0`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016774`
- `0x18002bd50`
- `0x18002c5b4`
- `0x18002dc8c`
- `0x18002e004`
- `0x18002fae4`
- `0x18002fd88`
- `0x180031c14`
- `0x1800343f0`
- `0x18008a840`
- `0x1800c6c38`
- `0x1800d9f2c`
- `0x180197608`
- `0x1801b7010`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800da0aa`
- `ntdll!RtlAcquirePrivilege` at `0x1800da0aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800da60c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800da60c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da67a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da70d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da8b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800daa17`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800daa77`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da67a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da70d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800da8b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800daa17`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800daa77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da649`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da1c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da2d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da336`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da3da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da4d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da1c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da2d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da336`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da3da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da4d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaf3`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800da147`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800da27d`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800da147`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800da27d`

## string_xrefs

- `0x1800da0c4`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x1800da63f`: `InstallEdgeRegistryState`
- `0x1800da605`: `edgeresetplugin.dll`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::SpecializationLayer::InstallEdgeInternal(
        __int64 a1,
        bool *a2,
        __int64 a3)
{
  int IsEdgeInstalled; // eax
  int Guid; // ebx
  int v9; // eax
  void *v10; // rcx
  __int64 v11; // rdx
  NTSTATUS v12; // eax
  int v13; // eax
  unsigned int KeyW; // eax
  int v15; // eax
  __int64 v16; // rdx
  HKEY v17; // rcx
  unsigned int v18; // eax
  struct _GUID *v19; // rdx
  __int64 v20; // rdx
  HKEY v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  struct _SECURITY_ATTRIBUTES *v25; // r8
  struct Path *v26; // rdx
  int SystemDrivePath; // eax
  HMODULE Library; // rax
  const char *v29; // r9
  HMODULE v30; // r14
  FARPROC ProcAddress; // rax
  const char *v32; // r9
  __int64 (__fastcall *v33)(void *, void *, HKEY, HKEY); // rsi
  HKEY v34; // rbx
  HKEY v35; // rdi
  int v36; // eax
  const char *v37; // r9
  unsigned int v38; // r15d
  int v39; // eax
  int v40; // [rsp+20h] [rbp-E0h]
  _BYTE v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  PVOID ReturnedState; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  ULONG Privilege[2]; // [rsp+78h] [rbp-88h] BYREF
  void *v45; // [rsp+80h] [rbp-80h] BYREF
  char *v46; // [rsp+88h] [rbp-78h]
  _WORD v47[8]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v49[8]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v51[8]; // [rsp+D0h] [rbp-30h] BYREF
  void *v52[2]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v53[8]; // [rsp+F0h] [rbp-10h] BYREF
  void *v54; // [rsp+100h] [rbp+0h] BYREF
  char *v55; // [rsp+108h] [rbp+8h]
  _WORD v56[8]; // [rsp+110h] [rbp+10h] BYREF
  int v57; // [rsp+120h] [rbp+20h]
  int v58; // [rsp+124h] [rbp+24h]
  void *v59[2]; // [rsp+128h] [rbp+28h] BYREF
  _WORD v60[8]; // [rsp+138h] [rbp+38h] BYREF
  const wchar_t *v61; // [rsp+148h] [rbp+48h]
  __int64 v62; // [rsp+150h] [rbp+50h]
  void *v63[2]; // [rsp+158h] [rbp+58h] BYREF
  _WORD v64[8]; // [rsp+168h] [rbp+68h] BYREF
  void *v65[2]; // [rsp+178h] [rbp+78h] BYREF
  _WORD v66[8]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v67; // [rsp+198h] [rbp+98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v41[0] = 0;
  IsEdgeInstalled = Container::Manager::Core::Details::IsEdgeInstalled((Container::Manager::Core::Details *)v41, a2);
  Guid = IsEdgeInstalled;
  if ( IsEdgeInstalled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)IsEdgeInstalled,
      v40);
    return (unsigned int)Guid;
  }
  if ( !v41[0] )
    return 0;
  v45 = v47;
  v46 = (char *)v47;
  v47[0] = 0;
  v9 = Csl::GuidToString(a1 + 88, &v45);
  Guid = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v9,
      v40);
    v10 = v45;
    if ( v45 == v47 )
      return (unsigned int)Guid;
LABEL_7:
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)Guid;
  }
  lpSubKey[0] = v49;
  lpSubKey[1] = v49;
  v49[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpSubKey,
                           v45,
                           (v46 - (_BYTE *)v45) >> 1) )
  {
    v11 = 1516;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)0x8007000ELL,
      v40);
LABEL_123:
    if ( lpSubKey[0] != v49 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v45 != v47 )
      operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpSubKey,
                           L"_SOFTWARE",
                           9) )
  {
    v11 = 1517;
    goto LABEL_10;
  }
  ReturnedState = 0;
  Privilege[0] = 17;
  Privilege[1] = 18;
  v12 = RtlAcquirePrivilege(Privilege, 2u, 2u, &ReturnedState);
  if ( v12 < 0 )
  {
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x52,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
            (const char *)(unsigned int)v12,
            v40);
    Guid = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)(unsigned int)v13,
        v40);
      goto LABEL_16;
    }
  }
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0], *(LPCWSTR *)(a1 + 32));
  if ( KeyW )
  {
    Guid = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x5F7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
             (const char *)KeyW,
             v40);
    goto LABEL_16;
  }
  hKey = 0;
  v15 = Csl::OpenRegistryKey(-2147483646, lpSubKey[0], 983103, &hKey);
  Guid = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v15,
      v40);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_16;
  }
  v50[0] = v51;
  v50[1] = v51;
  v51[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v50,
                           v45,
                           (v46 - (_BYTE *)v45) >> 1) )
  {
    v16 = 1537;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)0x8007000ELL,
      v40);
    goto LABEL_28;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v50,
                           L"_SYSTEM",
                           7) )
  {
    v16 = 1538;
    goto LABEL_27;
  }
  v18 = RegLoadKeyW(HKEY_LOCAL_MACHINE, v50[0], *(LPCWSTR *)a1);
  if ( v18 )
  {
    Guid = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x606,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
             (const char *)v18,
             v40);
LABEL_36:
    if ( v50[0] != v51 )
      operator delete((void *)v50[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_16:
    Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
    if ( lpSubKey[0] != v49 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    v10 = v45;
    if ( v45 == v47 )
      return (unsigned int)Guid;
    goto LABEL_7;
  }
  *(_QWORD *)Privilege = 0;
  Guid = Csl::OpenRegistryKey(-2147483646, v50[0], 983103, Privilege);
  if ( Guid < 0 )
  {
    v20 = 1548;
    goto LABEL_43;
  }
  v67 = 0;
  Guid = Csl::CreateGuid((Csl *)&v67, v19);
  if ( Guid < 0 )
  {
    v20 = 1553;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)Guid,
      v40);
    v21 = *(HKEY *)Privilege;
    if ( !*(_QWORD *)Privilege )
      goto LABEL_36;
LABEL_52:
    RegCloseKey(v21);
    goto LABEL_36;
  }
  v54 = v56;
  v55 = (char *)v56;
  v56[0] = 0;
  v22 = Csl::GuidToString(&v67, &v54);
  Guid = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x614,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v22,
      v40);
    goto LABEL_49;
  }
  v52[0] = v53;
  v52[1] = v53;
  v53[0] = 0;
  Guid = Container::Manager::Core::Details::Layer::GetResourcePath(*(_QWORD *)(a1 + 64), 3, v52);
  if ( Guid < 0 )
  {
    v23 = 1560;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)Guid,
      v40);
LABEL_56:
    if ( v52[0] != v53 )
      operator delete(v52[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_49:
    if ( v54 != v56 )
      operator delete(v54, (const struct std::nothrow_t *)&std::nothrow);
    v21 = *(HKEY *)Privilege;
    if ( !*(_QWORD *)Privilege )
      goto LABEL_36;
    goto LABEL_52;
  }
  v61 = L"Scratch";
  v62 = 7;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v52) )
  {
    v24 = 1562;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)0x8007000ELL,
      v40);
LABEL_61:
    if ( v52[0] != v53 )
      operator delete(v52[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v54 != v56 )
      operator delete(v54, (const struct std::nothrow_t *)&std::nothrow);
    if ( *(_QWORD *)Privilege )
      RegCloseKey(*(HKEY *)Privilege);
LABEL_28:
    if ( v50[0] != v51 )
      operator delete((void *)v50[0], (const struct std::nothrow_t *)&std::nothrow);
    v17 = hKey;
    if ( !hKey )
      goto LABEL_122;
    goto LABEL_121;
  }
  v61 = (const wchar_t *)v54;
  v62 = (v55 - (_BYTE *)v54) >> 1;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v52) )
  {
    v24 = 1563;
    goto LABEL_60;
  }
  Guid = Csl::CreateDirectoryRecursive((Csl *)v52, 0, v25);
  if ( Guid < 0 )
  {
    v23 = 1565;
    goto LABEL_55;
  }
  v59[0] = v60;
  v59[1] = v60;
  v60[0] = 0;
  SystemDrivePath = Csl::GetSystemDrivePath((Csl *)v59, v26);
  Guid = SystemDrivePath;
  if ( SystemDrivePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x622,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)SystemDrivePath,
      v40);
    goto LABEL_73;
  }
  v61 = L"Program Files (x86)\\Microsoft";
  v62 = 29;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v59) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x623,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)0x8007000ELL,
      v40);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_61;
  }
  Library = LoadLibraryExW(L"edgeresetplugin.dll", 0, 0x800u);
  v30 = Library;
  if ( !Library )
  {
    Guid = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x62C,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
             v29);
    goto LABEL_73;
  }
  ProcAddress = GetProcAddress(Library, "InstallEdgeRegistryState");
  v33 = (__int64 (__fastcall *)(void *, void *, HKEY, HKEY))ProcAddress;
  if ( !ProcAddress )
  {
    Guid = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x631,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
             v32);
    FreeLibrary(v30);
LABEL_73:
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_56;
  }
  v58 = 0;
  v57 = 0;
  LOBYTE(v40) = 0;
  v34 = *(HKEY *)Privilege;
  v35 = hKey;
  v36 = ((__int64 (__fastcall *)(void *, void *, HKEY, _QWORD))ProcAddress)(v59[0], v52[0], hKey, *(_QWORD *)Privilege);
  v38 = v36;
  if ( v36 == -2147024774 )
  {
    v63[0] = v64;
    v63[1] = v64;
    v64[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                             v63,
                             (unsigned int)(v58 - 1)) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)0x8007000ELL,
        v40);
LABEL_107:
      if ( v63[0] != v64 )
        operator delete(v63[0], (const struct std::nothrow_t *)&std::nothrow);
      FreeLibrary(v30);
      if ( v59[0] != v60 )
        operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v52[0] != v53 )
        operator delete(v52[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v54 != v56 )
        operator delete(v54, (const struct std::nothrow_t *)&std::nothrow);
      if ( v34 )
        RegCloseKey(v34);
      if ( v50[0] != v51 )
        operator delete((void *)v50[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( !v35 )
        goto LABEL_122;
      v17 = v35;
LABEL_121:
      RegCloseKey(v17);
LABEL_122:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      goto LABEL_123;
    }
    v65[0] = v66;
    v65[1] = v66;
    v66[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                             v65,
                             (unsigned int)(v57 - 1)) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)0x8007000ELL,
        v40);
      if ( v65[0] != v66 )
        operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_107;
    }
    LOBYTE(v40) = 0;
    v39 = v33(v59[0], v52[0], v35, v34);
    v38 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)(unsigned int)v39,
        v40);
      if ( v65[0] != v66 )
        operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v63[0] != v64 )
        operator delete(v63[0], (const struct std::nothrow_t *)&std::nothrow);
      FreeLibrary(v30);
      goto LABEL_85;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a2,
      v63);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a3,
      v65);
    if ( v65[0] != v66 )
      operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v63[0] != v64 )
      operator delete(v63[0], (const struct std::nothrow_t *)&std::nothrow);
    FreeLibrary(v30);
    if ( v59[0] != v60 )
      operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v52[0] != v53 )
      operator delete(v52[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v54 != v56 )
      operator delete(v54, (const struct std::nothrow_t *)&std::nothrow);
    if ( v34 )
      RegCloseKey(v34);
    if ( v50[0] != v51 )
      operator delete((void *)v50[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v35 )
      RegCloseKey(v35);
    Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
    if ( lpSubKey[0] != v49 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v45 != v47 )
      operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  if ( v36 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x644,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      v37);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x645,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
    (const char *)(unsigned int)v36,
    v40);
  FreeLibrary(v30);
LABEL_85:
  if ( v59[0] != v60 )
    operator delete(v59[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v52[0] != v53 )
    operator delete(v52[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v54 != v56 )
    operator delete(v54, (const struct std::nothrow_t *)&std::nothrow);
  if ( v34 )
    RegCloseKey(v34);
  if ( v50[0] != v51 )
    operator delete((void *)v50[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v35 )
    RegCloseKey(v35);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  if ( lpSubKey[0] != v49 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v45 != v47 )
    operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
  return v38;
}

```

## disassembly

```asm
0x1800d9f2c  mov     [rsp-8+arg_18], rbx
0x1800d9f31  push    rbp
0x1800d9f32  push    rsi
0x1800d9f33  push    rdi
0x1800d9f34  push    r12
0x1800d9f36  push    r13
0x1800d9f38  push    r14
0x1800d9f3a  push    r15
0x1800d9f3c  lea     rbp, [rsp-0B0h]
0x1800d9f44  sub     rsp, 1B0h
0x1800d9f4b  mov     rax, cs:__security_cookie
0x1800d9f52  xor     rax, rsp
0x1800d9f55  mov     [rbp+0E0h+var_38], rax
0x1800d9f5c  mov     r13, r8
0x1800d9f5f  mov     r12, rdx
0x1800d9f62  mov     rdi, rcx
0x1800d9f65  xor     r15d, r15d
0x1800d9f68  mov     [rsp+1E0h+var_180], r15b
0x1800d9f6d  lea     rcx, [rsp+1E0h+var_180]; this
0x1800d9f72  call    ?IsEdgeInstalled@Details@Core@Manager@Container@@YAJAEA_N@Z; Container::Manager::Core::Details::IsEdgeInstalled(bool &)
0x1800d9f77  mov     ebx, eax
0x1800d9f79  test    eax, eax
0x1800d9f7b  jns     short loc_1800D9F9F
0x1800d9f7d  mov     rcx, [rbp+0E8h]; this
0x1800d9f84  mov     r9d, eax; char *
0x1800d9f87  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d9f8e  mov     edx, 5E0h; void *
0x1800d9f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9f98  mov     eax, ebx
0x1800d9f9a  jmp     loc_1800DAB35
0x1800d9f9f  cmp     [rsp+1E0h+var_180], r15b
0x1800d9fa4  jz      loc_1800DAB33
0x1800d9faa  lea     rax, [rbp+0E0h+var_150]
0x1800d9fae  mov     [rbp+0E0h+var_160], rax
0x1800d9fb2  lea     rax, [rbp+0E0h+var_150]
0x1800d9fb6  mov     [rbp+0E0h+var_158], rax
0x1800d9fba  mov     [rbp+0E0h+var_150], r15w
0x1800d9fbf  lea     rcx, [rdi+58h]
0x1800d9fc3  lea     rdx, [rbp+0E0h+var_160]
0x1800d9fc7  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800d9fcc  mov     ebx, eax
0x1800d9fce  test    eax, eax
0x1800d9fd0  jns     short loc_1800DA008
0x1800d9fd2  mov     rcx, [rbp+0E8h]; this
0x1800d9fd9  mov     r9d, eax; char *
0x1800d9fdc  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d9fe3  mov     edx, 5E8h; void *
0x1800d9fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9fed  lea     rax, [rbp+0E0h+var_150]
0x1800d9ff1  mov     rcx, [rbp+0E0h+var_160]; void *
0x1800d9ff5  cmp     rcx, rax
0x1800d9ff8  jz      short loc_1800D9F98
0x1800d9ffa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800da001  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da006  jmp     short loc_1800D9F98
0x1800da008  lea     rax, [rbp+0E0h+var_130]
0x1800da00c  mov     [rbp+0E0h+lpSubKey], rax
0x1800da010  lea     rax, [rbp+0E0h+var_130]
0x1800da014  mov     [rbp+0E0h+var_138], rax
0x1800da018  mov     [rbp+0E0h+var_130], r15w
0x1800da01d  mov     r8, [rbp+0E0h+var_158]
0x1800da021  mov     rdx, [rbp+0E0h+var_160]
0x1800da025  sub     r8, rdx
0x1800da028  sar     r8, 1
0x1800da02b  lea     rcx, [rbp+0E0h+lpSubKey]
0x1800da02f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800da034  test    al, al
0x1800da036  jnz     short loc_1800DA062
0x1800da038  mov     edx, 5ECh; void *
0x1800da03d  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da044  mov     r9d, 8007000Eh; char *
0x1800da04a  mov     rcx, [rbp+0E8h]; this
0x1800da051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da056  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da05d  jmp     loc_1800DA946
0x1800da062  mov     r8d, 9
0x1800da068  lea     rdx, aSoftware_1; "_SOFTWARE"
0x1800da06f  lea     rcx, [rbp+0E0h+lpSubKey]
0x1800da073  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800da078  test    al, al
0x1800da07a  jnz     short loc_1800DA083
0x1800da07c  mov     edx, 5EDh
0x1800da081  jmp     short loc_1800DA03D
0x1800da083  mov     [rsp+1E0h+ReturnedState], r15
0x1800da088  mov     [rsp+1E0h+Privilege], 11h
0x1800da090  mov     [rsp+1E0h+Privilege+4], 12h
0x1800da098  lea     r9, [rsp+1E0h+ReturnedState]; ReturnedState
0x1800da09d  mov     edx, 2; NumPriv
0x1800da0a2  mov     r8d, edx; Flags
0x1800da0a5  lea     rcx, [rsp+1E0h+Privilege]; Privilege
0x1800da0aa  call    cs:__imp_RtlAcquirePrivilege
0x1800da0b1  nop     dword ptr [rax+rax+00h]
0x1800da0b6  test    eax, eax
0x1800da0b8  jns     short loc_1800DA135
0x1800da0ba  mov     rcx, [rbp+0E8h]; this
0x1800da0c1  mov     r9d, eax; char *
0x1800da0c4  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800da0cb  mov     edx, 52h ; 'R'; void *
0x1800da0d0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800da0d5  mov     ebx, eax
0x1800da0d7  test    eax, eax
0x1800da0d9  jns     short loc_1800DA135
0x1800da0db  mov     rcx, [rbp+0E8h]; this
0x1800da0e2  mov     r9d, eax; char *
0x1800da0e5  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da0ec  mov     edx, 5F3h; void *
0x1800da0f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da0f6  lea     rcx, [rsp+1E0h+ReturnedState]; this
0x1800da0fb  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800da100  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da107  lea     rax, [rbp+0E0h+var_130]
0x1800da10b  mov     rcx, [rbp+0E0h+lpSubKey]; void *
0x1800da10f  cmp     rcx, rax
0x1800da112  jz      short loc_1800DA11C
0x1800da114  mov     rdx, rsi; struct std::nothrow_t *
0x1800da117  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da11c  lea     rax, [rbp+0E0h+var_150]
0x1800da120  mov     rcx, [rbp+0E0h+var_160]
0x1800da124  cmp     rcx, rax
0x1800da127  jz      loc_1800D9F98
0x1800da12d  mov     rdx, rsi
0x1800da130  jmp     loc_1800DA001
0x1800da135  mov     r8, [rdi+20h]; lpFile
0x1800da139  mov     rdx, [rbp+0E0h+lpSubKey]; lpSubKey
0x1800da13d  mov     rsi, 0FFFFFFFF80000002h
0x1800da144  mov     rcx, rsi; hKey
0x1800da147  call    cs:__imp_RegLoadKeyW
0x1800da14e  nop     dword ptr [rax+rax+00h]
0x1800da153  test    eax, eax
0x1800da155  jz      short loc_1800DA176
0x1800da157  mov     rcx, [rbp+0E8h]; this
0x1800da15e  mov     r9d, eax; char *
0x1800da161  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da168  mov     edx, 5F7h; void *
0x1800da16d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800da172  mov     ebx, eax
0x1800da174  jmp     short loc_1800DA0F6
0x1800da176  mov     [rsp+1E0h+hKey], r15
0x1800da17b  lea     r9, [rsp+1E0h+hKey]
0x1800da180  mov     r8d, 0F003Fh
0x1800da186  mov     rdx, [rbp+0E0h+lpSubKey]
0x1800da18a  mov     rcx, rsi
0x1800da18d  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800da192  mov     ebx, eax
0x1800da194  test    eax, eax
0x1800da196  jns     short loc_1800DA1D2
0x1800da198  mov     rcx, [rbp+0E8h]; this
0x1800da19f  mov     r9d, eax; char *
0x1800da1a2  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da1a9  mov     edx, 5FDh; void *
0x1800da1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da1b3  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800da1b8  test    rcx, rcx
0x1800da1bb  jz      loc_1800DA0F6
0x1800da1c1  call    cs:__imp_RegCloseKey
0x1800da1c8  nop     dword ptr [rax+rax+00h]
0x1800da1cd  jmp     loc_1800DA0F6
0x1800da1d2  lea     rax, [rbp+0E0h+var_110]
0x1800da1d6  mov     [rbp+0E0h+var_120], rax
0x1800da1da  lea     rax, [rbp+0E0h+var_110]
0x1800da1de  mov     [rbp+0E0h+var_118], rax
0x1800da1e2  mov     [rbp+0E0h+var_110], r15w
0x1800da1e7  mov     r8, [rbp+0E0h+var_158]
0x1800da1eb  mov     rdx, [rbp+0E0h+var_160]
0x1800da1ef  sub     r8, rdx
0x1800da1f2  sar     r8, 1
0x1800da1f5  lea     rcx, [rbp+0E0h+var_120]
0x1800da1f9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800da1fe  test    al, al
0x1800da200  jnz     short loc_1800DA24F
0x1800da202  mov     edx, 601h; void *
0x1800da207  mov     r9d, 8007000Eh; char *
0x1800da20d  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da214  mov     rcx, [rbp+0E8h]; this
0x1800da21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da220  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da227  lea     rax, [rbp+0E0h+var_110]
0x1800da22b  mov     rcx, [rbp+0E0h+var_120]; void *
0x1800da22f  cmp     rcx, rax
0x1800da232  jz      short loc_1800DA23C
0x1800da234  mov     rdx, rsi; struct std::nothrow_t *
0x1800da237  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da23c  mov     rcx, [rsp+1E0h+hKey]
0x1800da241  test    rcx, rcx
0x1800da244  jz      loc_1800DA93C
0x1800da24a  jmp     loc_1800DA930
0x1800da24f  mov     r14d, 7
0x1800da255  mov     r8d, r14d
0x1800da258  lea     rdx, aSystem_0; "_SYSTEM"
0x1800da25f  lea     rcx, [rbp+0E0h+var_120]
0x1800da263  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800da268  test    al, al
0x1800da26a  jnz     short loc_1800DA273
0x1800da26c  mov     edx, 602h
0x1800da271  jmp     short loc_1800DA207
0x1800da273  mov     r8, [rdi]; lpFile
0x1800da276  mov     rdx, [rbp+0E0h+var_120]; lpSubKey
0x1800da27a  mov     rcx, rsi; hKey
0x1800da27d  call    cs:__imp_RegLoadKeyW
0x1800da284  nop     dword ptr [rax+rax+00h]
0x1800da289  test    eax, eax
0x1800da28b  jz      short loc_1800DA2EB
0x1800da28d  mov     rcx, [rbp+0E8h]; this
0x1800da294  mov     r9d, eax; char *
0x1800da297  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da29e  mov     edx, 606h; void *
0x1800da2a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800da2a8  mov     ebx, eax
0x1800da2aa  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da2b1  lea     rax, [rbp+0E0h+var_110]
0x1800da2b5  mov     rcx, [rbp+0E0h+var_120]; void *
0x1800da2b9  cmp     rcx, rax
0x1800da2bc  jz      short loc_1800DA2C6
0x1800da2be  mov     rdx, rsi; struct std::nothrow_t *
0x1800da2c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da2c6  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800da2cb  test    rcx, rcx
0x1800da2ce  jz      short loc_1800DA2DC
0x1800da2d0  call    cs:__imp_RegCloseKey
0x1800da2d7  nop     dword ptr [rax+rax+00h]
0x1800da2dc  lea     rcx, [rsp+1E0h+ReturnedState]; this
0x1800da2e1  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800da2e6  jmp     loc_1800DA107
0x1800da2eb  mov     qword ptr [rsp+1E0h+Privilege], r15
0x1800da2f0  lea     r9, [rsp+1E0h+Privilege]
0x1800da2f5  mov     r8d, 0F003Fh
0x1800da2fb  mov     rdx, [rbp+0E0h+var_120]
0x1800da2ff  mov     rcx, rsi
0x1800da302  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800da307  mov     ebx, eax
0x1800da309  test    eax, eax
0x1800da30b  jns     short loc_1800DA347
0x1800da30d  mov     edx, 60Ch; void *
0x1800da312  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da319  mov     r9d, ebx; char *
0x1800da31c  mov     rcx, [rbp+0E8h]; this
0x1800da323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da328  mov     rcx, qword ptr [rsp+1E0h+Privilege]; hKey
0x1800da32d  test    rcx, rcx
0x1800da330  jz      loc_1800DA2AA
0x1800da336  call    cs:__imp_RegCloseKey
0x1800da33d  nop     dword ptr [rax+rax+00h]
0x1800da342  jmp     loc_1800DA2AA
0x1800da347  xorps   xmm0, xmm0
0x1800da34a  movups  [rbp+0E0h+var_48], xmm0
0x1800da351  lea     rcx, [rbp+0E0h+var_48]; this
0x1800da358  call    ?CreateGuid@Csl@@YAJAEAU_GUID@@@Z; Csl::CreateGuid(_GUID &)
0x1800da35d  mov     ebx, eax
0x1800da35f  test    eax, eax
0x1800da361  jns     short loc_1800DA36A
0x1800da363  mov     edx, 611h
0x1800da368  jmp     short loc_1800DA312
0x1800da36a  lea     rax, [rbp+0E0h+var_D0]
0x1800da36e  mov     [rbp+0E0h+var_E0], rax
0x1800da372  lea     rax, [rbp+0E0h+var_D0]
0x1800da376  mov     [rbp+0E0h+var_D8], rax
0x1800da37a  mov     [rbp+0E0h+var_D0], r15w
0x1800da37f  lea     rdx, [rbp+0E0h+var_E0]
0x1800da383  lea     rcx, [rbp+0E0h+var_48]
0x1800da38a  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800da38f  mov     ebx, eax
0x1800da391  test    eax, eax
0x1800da393  jns     short loc_1800DA3EB
0x1800da395  mov     rcx, [rbp+0E8h]; this
0x1800da39c  mov     r9d, eax; char *
0x1800da39f  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da3a6  mov     edx, 614h; void *
0x1800da3ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da3b0  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da3b7  lea     rax, [rbp+0E0h+var_D0]
0x1800da3bb  mov     rcx, [rbp+0E0h+var_E0]; void *
0x1800da3bf  cmp     rcx, rax
0x1800da3c2  jz      short loc_1800DA3CC
0x1800da3c4  mov     rdx, rsi; struct std::nothrow_t *
0x1800da3c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800da3cc  mov     rcx, qword ptr [rsp+1E0h+Privilege]; hKey
0x1800da3d1  test    rcx, rcx
0x1800da3d4  jz      loc_1800DA2B1
0x1800da3da  call    cs:__imp_RegCloseKey
0x1800da3e1  nop     dword ptr [rax+rax+00h]
0x1800da3e6  jmp     loc_1800DA2B1
0x1800da3eb  lea     rax, [rbp+0E0h+var_F0]
0x1800da3ef  mov     [rbp+0E0h+var_100], rax
0x1800da3f3  lea     rax, [rbp+0E0h+var_F0]
0x1800da3f7  mov     [rbp+0E0h+var_F8], rax
0x1800da3fb  mov     [rbp+0E0h+var_F0], r15w
0x1800da400  lea     r8, [rbp+0E0h+var_100]
0x1800da404  mov     edx, 3
0x1800da409  mov     rcx, [rdi+40h]
0x1800da40d  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800da412  mov     ebx, eax
0x1800da414  test    eax, eax
0x1800da416  jns     short loc_1800DA458
0x1800da418  mov     edx, 618h; void *
0x1800da41d  mov     r9d, ebx; char *
0x1800da420  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800da427  mov     rcx, [rbp+0E8h]; this
0x1800da42e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da433  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800da43a  mov     rcx, [rbp+0E0h+var_100]; void *
  ... truncated ...
```
